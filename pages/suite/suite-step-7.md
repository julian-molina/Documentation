---
title:  Control Data Mining Operation
summary: Start and stop individual tasks, each task manager controlling multiple tasks, or all task managers at once.
sidebar: suite_sidebar
permalink: suite-step-7.html
toc: false
---

The data mining operation puts a load on your machine's CPU. If your hardware is basic, your machine may get slow. In that case, you may want to stop some of the processes. On the other hand, if your hardware handles the default processes fine, you may want to start calculating other indicators right away. The instructions below will teach you how to do both operations.

{% include note.html content="To experience how the system handles charts with combined exchanges and markets, you need to keep all task managers running as set automatically by the system. Even if your machine gets slow, and provided you can afford some time off, we encourage you to keep the bots running for a while. It shouldn't take more than an hour to download all default markets. Once bots reach the present datetime you can safely stop all task managers and still enjoy the demo charts." %}

{% include tip.html content="During the regular use of the system, there are instances in which you will need to have bots running, and situations in which having a live data feed from exchanges is not necessary. For example, if you are designing a strategy, backtesting, setting up charts, or performing any sort of system configuration, you do not need to have your data mining operation running at all. The situations in which you need a live data feed are mainly active market monitoring and trading sessions that involve interacting with the exchange, such as paper trading, forward testing, and live trading sessions." %}

To control which bots get to run, you control which <a data-toggle="tooltip" data-original-title="{{site.data.network.task}}">tasks</a> get to run. You may start or stop individual tasks, or the whole task manager controlling a group of tasks. For the time being, and until you understand what each of the bots does, you will learn how to operate task managers&mdash;that said, tasks work pretty much in the same way. 

Remember, each Masters task manager on the data mining node controls the bots processing data from a specific exchange and market.

## Start Here

**1. To stop a task manager**, select *Stop All Tasks* on the menu of the corresponding task manager.

{% include image.html file='how-to/data-mining-01.gif' url='yes' max-width='100' caption='To stop all tasks on a task manager, click *Stop All Tasks* on the menu.' %}

**2. To start the Sparta task managers**, select *Run All Tasks* on the menu. If your machine is coping well with the processes running by default, you may want to run all of the Sparta task managers, to use all currently available indicators. 

{% include image.html file='how-to/data-mining-02.gif' url='yes' max-width='100' caption='To start all tasks on a task manager, click *Run All Tasks* on the menu.' %}

**3. To start or stop all task managers at once**, select the corresponding button on the data mining node menu.

{% include image.html file='how-to/data-mining-03.gif' url='yes' max-width='100' caption='To start or stop all task managers, click the corresponding button on the menu.' %}

{% include note.html content="It takes about one minute to stop a task gracefully, as the corresponding bot is allowed to finish the processing cycle to guarantee data integrity. **Never close the console when bots are running; always stop all bots before.** You may, however, close your browser at any point. Once closed, you may always re-open the browser and get back to controlling your bots." %}


