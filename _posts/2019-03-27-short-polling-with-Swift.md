---
title: "Short-polling with Swift"
categories:
  - iOS
  - Swift
tags:
  - iOS
  - Swift
  - Short Polling
---

Repeating tasks, e.g. fetching APIs, are tasks/block codes need to be excuted every interval time. I sometimes have to deal with them. And they sometimes become massive with a lot of timer and release timer things. So I decide to write a simple short-polling center in Swift. [Short-polling repo](https://github.com/tuledev/short-polling)

What I need a polling center do

- Excute a task every interval
- Excute tasks in a single background queue
- Easy to enable/disable a polling
- Seperate each polling

What I will implement
 
- Protocol for polling item. So I can create my own polling item easily.
  
  - Have uid so I can manage them
  - Can config time interval
  - Have a handler for excuting
- Polling center. For managing polling item.
  
  - Singleton object
  - Have a queue for every tasks can excute in background queue
  - Have a timer for each Pollingable item
  - Enable/disable Pollingable item in a queue also


## 1. Protocol for Pollingable item
```swift
protocol Pollingable {
  // default uid for polling
  func uid() -> String
  static func uid() -> String
  // interval in second
  func interval() -> Int
  // invoke handler every interval
  func eventHandler() -> (() -> Void)
}
extension Pollingable where Self: NSObject {
  func uid() -> String {
    return String(describing: Self.self)
  }
  
  static func uid() -> String {
    return String(describing: Self.self)
  }
}
```

## 2. Polling Center

#### Singleton center
```swift
  private static var sharedInstance: PollingCenter = {
    let pollingCenter = PollingCenter()
    return pollingCenter
  }()
  
  static func shared() -> PollingCenter {
    return sharedInstance
  }
```

#### Queue for timer
``` Swift
  private let serialQueueChanging = DispatchQueue(label: "serialQueuePollingCenter")
```

#### Timer for each Pollingable item
```swift
  private func createTimer(polling: Pollingable) -> DispatchSourceTimer {
    let queue = DispatchQueue.global(qos: .background)
    let timer = DispatchSource.makeTimerSource(queue: queue)
    timer.schedule(deadline: .now(), repeating: .seconds(polling.interval()))
    timer.setEventHandler(handler: {
      polling.eventHandler()()
    })
    return timer
  }
```

I've almost done for creating center. Now I will add polling items and let them running in queue.

#### Resume/Pause Pollingable items via polling uid
```swift
  fileprivate func resumePolling(_ uid: String) {
    if let polling = self.pollings[uid], let state = self.pollingStates[uid] {
      if state == false {
        self.pollingStates[uid] = true
        polling.resume()
      }
    }
  }
  
  fileprivate func pausePolling(_ uid: String) {
    if let polling = self.pollings[uid], let state = self.pollingStates[uid] {
      if state == true {
        self.pollingStates[uid] = false
        polling.suspend()
      }
    }
  }
```

I make them private because they have to be executed in a queue, so they won't be conflicted each others.


#### Add Pollingable item to Polling Center
```swift
  func addPolling(_ polling: Pollingable) {
    // check if uid is added
    if pollings.index(forKey: polling.uid()) == nil {
      // create timer for polling item
      pollings[polling.uid()] = createTimer(polling: polling)
      // defaut disable
      pollingStates[polling.uid()] = false
    }
  }
```

#### Enable/Disable Pollingable item
```swift
  func enablePolling(_ uid: String) {
    self.serialQueueChanging.sync {
      self.resumePolling(uid)
    }
  }
  func disablePolling(_ uid: String) {
    self.serialQueueChanging.sync {
      self.pausePolling(uid)
    }
  }
```

Excute resume/pause Polling item in the queue so they won't be conficted.

Done. Now I can use this simple center:

```swift
let pollingCenter = PollingCenter()
let printPolling = PrintPolling() // Pollingable item
pollingCenter.addPolling(printPolling)
pollingCenter.enablePolling(printPolling.uid()) // item's running now
```

[Source code](https://github.com/tuledev/short-polling)
