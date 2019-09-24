---
title: Using Telegram bot as a real-time logger
categories:
  - Logger
  - Swift
tags:
  - Swift
  - Telegram
---

# 2019-03-07-telegram-bot-as-a-real-time-logger

Telegram is the best messaging application I have ever used. In this post I want to focus on a feature that using bot to act as a real-time logger. All information about Telegram bots can be found [here](https://core.telegram.org/bots)

How to get statuses of the running job or anything that you want to tracking? How to get notification when your system has a trouble?... Basically, Telegram provides an API to push message to Telegram chat. And we can use it to tracking what we want with 3 steps: 

1. Create Telegram bot, and get bot token 

2. Create Telegram group, and get chat ID 

3. Send message to Telegram group

## Create Telegram bot, and get bot token

* Search **BotFather** in Telegram.
* Create new bot with command `/newbot`.
* Choose a name for your bot, after that you can get the **BOT\_TOKEN** of the bot to access the HTTP API.
* Open your bot, press **Start**

## Create Telegram group, and get chat ID

* Create a Telegram group, add the bot to the group.
* Get the chat group id by paste this to a browser `https://api.telegram.org/bot[BOT_TOKEN]/getUpdates`

  \(If you dont get result array, try to remove bot and then add again to the group\)

  Parse the reponse JSON you can see something like: `{"id":-123456789,"title":"tuledev","type":"group","all_members_are_administrators":true}`

  `-123456789` is the ID of the group.

## Send message to Telegram group

* After getting the BOT\_TOKEN and GROUP\_ID, it's so easy to send message to the group via API

  `https://api.telegram.org/bot<BOT_TOKEN>/sendMessage?chat_id=<GROUP_ID>&text=<MESSAGE_TEXT>`

  Example with curl:

  `curl -s -X POST https://api.telegram.org/bot[BOT_TOKEN]/sendMessage -d chat_id=-123456789 -d text="Hello Bot"`

  Example with Swift:

  ```swift
  func sendTelegram(_ message: String) {
    Alamofire.request("https://api.telegram.org/bot\(BOT_TOKEN)/sendMessage",
      method: .post,
      parameters: ["chat_id": CHAT_ID, "text": message],
      headers:nil)
  }
  sendTelegram("Hello Bot")
  ```

## Pros:

* Real-time like
* Very easy to setup
* Free

## Cons:

* Have limits. [How to avoid hitting limits?](https://core.telegram.org/bots/faq#my-bot-is-hitting-limits-how-do-i-avoid-this)

