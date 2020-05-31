---
title:  Snapshots
summary: "Snapshots are CSV files containing all trades produced during a backtesting session, and the values for each indicator property used throughout the trading system."
sidebar: suite_sidebar
permalink: suite-snapshots.html
toc: false
---

Beyond simulations, the trading bot produces an additional output called *Snapshots*. 

A snapshot is a flat file in the CSV format listing every trade in a backtesting session. CSV files may be imported and analyzed in spreadsheet software. Columns represent properties that may be available as [internal variables](suite-internal-variables.html) or indicator properties, and rows represent trades.

Two snapshots are created for each backtesting session: one for the <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.trigger-on_event}}">trigger-on event</a> and one for the <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.take_position_event}}">take position event</a>.

The first eight columns in a snapshot file are the following:

* **Trade Number**: A sequential number starting from 1.

* **Close Datetime**: the datetime corresponding to the instant of the exit of the trade.   

* **Strategy**: The name of the strategy that produced the trade.

* **Trigger On Situation**: The name of the situation that triggered on the strategy.

* **Take Position Situation**: The name of the situation responsible for taking the position.

* **Result**: The result of the trade expressed as a *HIT* or *FAIL*.

* **ROI**: The return of investment of the particular trade.

* **Exit Type**: The type of exit of the trade expressed as *Close@StopLoss* or *Close@TakeProfit*.

The rest of the columns in the file provide the value of each indicator property used throughout the trading system.

{% include tip.html content="If you would like the snapshot to include indicator properties that are not being used in the trading system, you may create a dummy situation that would always evaluate ```false```, and add as many conditions as you wish, including all the indicator properties you may be interested in, for the time frames you may be interested in. To make sure the situation always evaluates ```false``` use the following piece of code in the first condition: ```{false}```." %}

You may find snapshots in the following path:

```Data-Storage\[Exchange]\[Market]\TradingEngines\Protocol-Engine\Output\[Backtesting-Session-Folder]\Snapshots\[Multi-Period-Market or Multi-Period-Daily]\[Time Frame]```

For example:

{% include image.html file='trading-system/Snapshot-Path.PNG' url='yes' max-width='100' caption='\Data-Storage\Binance\BTC-USDT\TradingEngines\Protocol-Engine\Output\Back-BBTB-5d72321e-97e7-404f-8272-809dbbf4db35\Snapshots\Multi-Period-Market\01-hs' %}
