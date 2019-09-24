---
title: >-
  An easy way to instantiate UIViewController/UIView from Storyboard/Xib with
  Generic in Swift
categories:
  - iOS
tags:
  - iOS
  - Swift
---

# 2019-02-04-generic-loading-ios

As iOS developers, we already know the basic load/instantiate an `UIViewController` from Storyboard is

```swift
let storyboard = UIStoryboard(name: "Main", bundle: nil)
let loginViewController = storyboard.instantiateViewController(withIdentifier: "Login") as? LoginViewController
```

or `UIView` from Xib

```swift
let view = Bundle.main.loadNibNamed("WelcomeView", owner: nil, options: nil)?.first
```

In this post, I just want to suggest a generic way:

This requires the **Storyboard ID** of `UIViewController` in Storyboard is same as **it’s name**, or the **Xib’s name** have the same **name as UIView**.

Using:

