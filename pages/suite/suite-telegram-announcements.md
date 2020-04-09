---
title:  Telegram Announcements
summary: "Setup a Telegram bot to broadcast the activity of trading sessions to a Telegram group. You may produce plain-text or dynamic-content announcements at every event in your trading systems."
sidebar: suite_sidebar
permalink: suite-telegram-announcements.html
---

## Overview

The announcements feature allows users to set up notifications tied to specific events, and triggered once each particular event becomes active while running any of the available types of trading sessions. 

You may use this feature to stay informed about the actions of your strategies while trading live, or to broadcast signals over a Telegram group while paper trading, for instance.

Supported events are:

* Trigger-on event
* Trigger-off event
* Take position event
* Stop and take profit next-phase events

In addition, you can implement announcements at the level of stop and take profit *phases*, a particular case that shall be discussed too.

The current implementation is based on broadcasting announcements via Telegram bots. The system uses Telegram's bots API to interact with a Telegram bot you will create. The bot will be added as a user in the Telegram group of your choice in which it will deliver the announcements as per the configuration you will set up in the system.

## Setting Up a Telegram Bot and a Telegram Group

Telegram's documentation features the page <a href="https://core.telegram.org/bots" rel="nofollow" rel="noopener" target="_blank">Bots: An introduction for developers</a>, where you may find all the details on how to use Telegram bots. You may choose to read Telegram's documentation or simple follow the next few steps, which have been extracted for your convenience:

**1. Go to Telegram and find the user <a href="https://telegram.me/botfather" rel="nofollow" rel="noopener" target="_blank">@BotFather</a>**. You may use the link or simply search for the user.

**2. Type and send ```/newbot```**. BotFather will ask you to pick a name for your bot. Once the name is set, it will respond with the token (a text string) to access the HTTP API.

You will need this token at a later time.

**3. Create the Telegram group** in which your bot will broadcast the announcements.

**4. Add your bot, and also, <a href="https://telegram.me/myidbot" rel="nofollow" rel="noopener" target="_blank">@myidbot</a> as users in the group**. 

**5. Type and send ```/getgroupid``` in the group**. IDBot will answer with the group's ID. 

You will need this ID at a later time.

## Setting Up the Telegram Bot in Superalgos

You will set up your bot in a backtesting session, so that you may easily test the announcements. 

**1. Go to any of your backtesting sessions and add a *Social Bot* node** using the session's menu. A social bot will be added along with a telegram bot.

**2. Select *Edit Telegram Bot* on the telegram bot menu** and replace the placeholder text with the actual *botToken* and *chatId* you got earlier.

For example:

```json
{ 
"botToken": "927642627:2B1QkNX2620C2B1ZTp9JrQUV04YKtJrQ2t4",
"chatId":-388158765
}
```

The system now has everything it needs to communicate with your Telegram bot.

## Create Your Announcements

You may create as many announcements as you wish, on any of the events listed in the [Overview](#overview) section above by clicking *Add Announcement* on the corresponding event node menu.

There are two different ways in which you may customize announcements:

* Plain text
* Dynamic content

### Plain Text

To set a plain text announcement, click *Edit Announcement* on the announcement node menu and set a message on the field *text*.

For example:

```json
{ 
"text": "WHB Triggered-on!"
}
```

### Dynamic Content

To broadcast more elaborate messages that may include dynamic values of any of the current indicators or internal variables, set the message in the formula attached to the announcement instead.

The typical set up for a dynamic message consists of building a string by alternating "text between double quotes" with variables, separating them with plus signs (+).

For example, a typical announcement formula for the take position event may look like this:

```
"Selling BTC at $" + candle.close.toFixed(0) + ", with stop at $" + stopLoss.toFixed(0) + " and TP target at $" +  takeProfit.toFixed(0)
```

```.toFixed(0)``` rounds the number to zero decimal places. The above formula would result in something like:

```
Selling BTC at $9703, with stop at $9896 and TP target at $9115
```

{% include note.html content="If your formula is valid, the system will ignore the plain text version you may have set up in the announcement configuration. If for any reason the formula results in an error, then the plain text version will be used." %}

#### Announcements on Stop and Take Profit Phases

We mentioned earlier that, beyond setting announcements on events, you may also implement announcements at the level of a stop or take profit phase. These are useful to broadcast the management of dynamic stop and take profit targets.

When implemented at the level of a phase, the announcement is triggered every time the value of the underlying variable (the stop or take profit target) changes. This is an important difference, as the value may change at every candle (if you are using formulas that use variables).

This could result in too many announcements in relatively short intervals.

The ```valueVariation``` parameter introduced in the announcement configuration may be used to filter out announcements until a certain threshold is achieved. The value you enter will set the percentage of variation that needs to occur before a new announcement is broadcasted.

For instance, ```"valueVariation": 0.5``` means a new announcement will be broadcasted every time the value of the underlying variable changes by 0.5%.

```json
{ 
"text": "Write here what you want to announce.",
"valueVariantion": 0.5
}
```

## Finishing the Setup

It is unlikely that you will want to use the announcements feature from within a backtesting session. A more likely scenario is you will want to use it with a paper trading session (to generate signals) or from a live trading session, to monitor the activity of your live trading.

All you need to do to finish your set up is detach the social bot node from the backtesting session and attach it to the session you wish to use it in. Make sure the corresponding tasks are stopped before detaching and attaching the social bot.

