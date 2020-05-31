---
title: Low-Frequency Trading
summary: "The Superalgos trading bot is currently optimized for low-frequency trading."
sidebar: suite_sidebar
permalink: suite-low-frequency-trading.html
toc: false
---

The <a data-toggle="tooltip" data-original-title="{{site.data.network.trading_bot_instance}}">trading bot</a> makes decisions upon the closing of the current candle. Superalgos manages <a data-toggle="tooltip" data-original-title="{{site.data.network.time_frame}}">time frames</a> as low as one minute. That is, one minute, is the highest frequency handled by the trading bot.

When a <a data-toggle="tooltip" data-original-title="{{site.data.network.session}}">trading session</a> is run on the ```01-min``` time frame, this is what you should expect to happen in terms of the time it takes to do all the required processing for the trading bot to make a decision and place an order at the exchange:

| Process | Estimated Time [s] | Comments | 
| :--- | :---: | :--- |
| Sensor Bot | 0 - 65 | The sensor bot runs (by default) every 60 seconds. Upon each execution, anything between 0 to 60 seconds may have passed since the last one-minute candle closed. On top of this the sensor execution time may range from 1 to 5 seconds, depending on several factors *(i.e.: your hardware, internet bandwidth, distance to the exchange, exchange response time, and so on...)* |
| Candles - Volumes indicator | 3 - 5 | This indicator is required most of the time, as it is the one processing the one-minute candles extracted from the exchange to turn it into candles for the rest of the time frames available. In this case, the processing time depends entirely on your hardware. |
| Other indicators | 3 - 5 | Indicators that depend exclusively on the data products produced by Candles - Volumes may process their products as soon as Candles - Volumes finishes. Indicators with nested dependencies need to wait for their dependencies to finish, thus they are not processed in parallel but in series. |
| Trading Bot | 1 - 5 | Depending on the complexity of your trading system, the number of dependencies that must be loaded, your hardware, and the same connectivity considerations discussed for the sensor bot, the trading bot may take several seconds to do the processing and place the order at the exchange.

In conclusion, depending on how many indicators the trading system uses, and what the dependencies are, you should expect anything between 30 to 120 seconds or more of lag from the instant the candle closed at the exchange until the order is placed. With that in mind, making trading decisions upon the lower time frames supported by the system may not be reasonable. Instead, time frames above 5 or 10 minutes may work best.