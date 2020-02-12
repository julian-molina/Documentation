---
title:  Types of Bots
summary: "There are three types of bots required to process data and to trade: sensors bots, indicators bots, and the trading bot."
sidebar: suite_sidebar
permalink: suite-types-of-bots.html
---

The system handles three different kinds of bots:

* **Sensor bots:** {{site.data.concepts.sensor_bot}}

* **Indicator bots:** {{site.data.concepts.indicator_bot}}

* **Trading bot:** {{site.data.concepts.trading_bot}}

These bots are defined in <a href="" data-toggle="tooltip" data-original-title="{{site.data.data_mine.data_mine}}">data mines</a>. That is, data mines hold the source code and configuration&mdash;the complete set of definitions&mdash;of these three kinds of bots.

Using any of these bots entails creating an instance of the bot definition, so that this instance may actually run the bot's code. This is done from within the network hierarchy.

A bot instance is a references to a bot as defined in a data mine. The instance of the bot runs the defined processes and generates the defined data products.