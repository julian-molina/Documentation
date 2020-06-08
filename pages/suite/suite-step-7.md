---
title:  Control the Data Mining Operation
summary: Start and stop individual tasks, each task manager controlling multiple tasks, or all task managers at once.
sidebar: suite_sidebar
permalink: suite-step-7.html
toc: false
---

To control which bots get to run, you start and stop <a data-toggle="tooltip" data-original-title="{{site.data.network.task}}">tasks</a> which in turn control bots. You may start or stop individual tasks, or the whole <a data-toggle="tooltip" data-original-title="{{site.data.network.task_manager}}">task manager</a> controlling a group of tasks. For the time being, and until you understand what each of the bots does, you will learn how to operate task managers. That said, tasks work pretty much in the same way. 

Remember, each task manager works with a certain <a data-toggle="tooltip" data-original-title="{{site.data.data_mine.data_mine}}">data mine<a/>&mdash;<a data-toggle="tooltip" data-original-title="{{site.data.concepts.masters_data_mine}}">Masters</a> or <a data-toggle="tooltip" data-original-title="{{site.data.concepts.sparta_data_mine}}">Sparta</a>&mdash;and within a certain <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market}}">market</a> in a certain <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_exchange}}">exchange</a>.

The data mining operation puts a load on your machine's CPU. If your hardware is basic, your machine may get slow. On the other hand, if your hardware handles the default processes fine, you may want to start calculating the rest of the Sparta indicators or even other markets right away. 

At this point, you are waiting for the Masters and Sparta bots to process all of Binance's BTC/USDT market. You don't *need* to stop or run any other tasks. The explanations following are meant to teach you how to control your data mining operation, but going through those steps is not required to continue with the next few in the guide.

{% include note.html content="To experience how the system handles charts with combined exchanges and markets, you may want to run the Masters task managers for the BTC/USDT markets from Bitfinex, and Bittrex, along with the ETH/USDT and DASH/USDT markets from Bittrex. Once bots reach the present datetime you may safely stop these task managers and still enjoy the demo charts." %}

{% include note.html content="To experience the rest of the indicators made available by the Sparta data mine, you may start the Sparta task manager for the BTC/USDT markets in Binance (only one Sparta indicator&mdash;EMA&mdash;is started by default). Once bots reach the present datetime you may safely stop the task manager and still enjoy the indicators on the charts." %}

{% include tip.html content="During the regular use of the system, there are instances in which you will need to have bots running, and situations in which having a live data feed from exchanges is not necessary. For example, if you are designing a strategy, backtesting, setting up charts, or performing any sort of system configuration, you do **not** need to have your data mining operation running at all. The situations in which you need a live data feed are mainly active market monitoring and trading sessions that involve interacting with the exchange, such as paper trading, forward testing, and live trading sessions. Also, it is possible to set up tasks to run on a separate machine and control the operation remotely in a [trading farm](suite-fundamental-trading-farms-concepts.html) configuration." %}



## Start Here

**1. To stop a task manager**, select *Stop All Tasks* on the menu of the corresponding task manager.

{% include image.html file='how-to/data-mining-01.gif' url='yes' max-width='100' caption='To stop all tasks on a task manager, click *Stop All Tasks* on the menu.' %}

**2. To start a task manager**, select *Run All Tasks* on the menu. 

{% include image.html file='how-to/data-mining-02.gif' url='yes' max-width='100' caption='To start all tasks on a task manager, click *Run All Tasks* on the menu.' %}

**3. To start or stop all task managers of a specific exchange**, select the corresponding button on the exchange tasks node menu.

**4. To start or stop all task managers in all exchanges**, select the corresponding button on the data mining node menu.

{% include important.html content="It takes about one minute to stop a task gracefully, as the corresponding bot is allowed to finish the processing cycle to guarantee data integrity. **Never close the console when bots are running; always stop all bots before.** You may, however, close your browser at any point. Once closed, you may always re-open the browser and get back to controlling your bots." %}


