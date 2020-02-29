---
title:  Pull Data from Exchanges and Process Indicators
summary: To pull data from exchanges, start the corresponding sensor bot tasks. To process indicators, start the associated indicator bot tasks.
sidebar: suite_sidebar
permalink: suite-step-6.html
toc: false
---

Superalgos puts you in control of the market data you will work with. To do that, the system uses a <a data-toggle="tooltip" data-original-title="{{site.data.concepts.sensor_bot}}">sensor bot</a> to pull 1-minute candles data from exchanges and store it in your machine (it is also possible to pull raw trades data). As the data starts building up, the system uses <a data-toggle="tooltip" data-original-title="{{site.data.concepts.indicator_bot}}">indicator bots</a> to process the raw data into more ellaborate <a data-toggle="tooltip" data-original-title="{{site.data.concepts.dataset}}">datasets</a> in the form of candles for all time frames, and all sorts of indicators.

The sensor bot fetches data starting from a configurable date. Once it reaches the present time, it continues connecting to the exchange once per minute, pulling data in a live stream. Indicators process data similarly and keep all your data up to date.

Depending on how you intend to use Superalgos, you may want to pull data from as far back as exchanges are willing to give. Such may be the case if you wish to backtest strategies.

On the other hand, if your interest lies in monitoring markets starting from the present time, then you most likely do not need historical data stretching that far in the past.

{% include important.html content="As hinted earlier, for your convenience, the system starts pulling data from exchanges as soon as you start it the first time. The current default is pulling the complete BTC/USDT and ETH/USDT markets from Binance, and one-year worth of the same markets from Bitfinex (limited by the exchange). At the same time, several basic indicators are fired up. These processes put a load on the CPU of your machine. If your hardware is basic, your machine may get slow. In that case, you may want to stop some of the processes. On the other hand, if your hardware handles the default process fine, you may want to start calculating other indicators right away. The instructions below will teach you how to do both operations." %}

## Start Here

**1. Open the design space** by pulling the slider to the top of the screen.

**2. Go to the <a data-toggle="tooltip" data-original-title="{{site.data.network.network}}">network hierarchy</a>**. 

{% include /how_to/find-a-hierarchy.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**3. Hover the mouse over the network <a data-toggle="tooltip" data-original-title="{{site.data.concepts.node}}">node</a>** and click the {% include inline_image.html file="icons/12-expand.png" %} button on the menu. This action expands the <a data-toggle="tooltip" data-original-title="{{site.data.concepts.hierarchy}}">hierarchy</a>.

**4. Follow the <a data-toggle="tooltip" data-original-title="{{site.data.concepts.structure_of_nodes}}">structure of nodes</a> until you find the <a data-toggle="tooltip" data-original-title="{{site.data.network.data_mining}}">data mining</a> node**. This is where <a data-toggle="tooltip" data-original-title="{{site.data.network.sensor_bot_instance}}">sensor bot instances</a> and <a data-toggle="tooltip" data-original-title="{{site.data.network.indicator_bot_instance}}">indicator bot instances</a> live and function. 

{% include image.html file='how-to/data-mining-00.gif' url='yes' max-width='100' caption='The data mining node groups all task managers controlling sensor and indicator bots.' %}

Notice how the hierarchy continues with several <a data-toggle="tooltip" data-original-title="{{site.data.network.task_manager}}">task managers</a>. 

Each task manager has a label that starts with the words <a data-toggle="tooltip" data-original-title="{{site.data.concepts.masters_data_mine}}">Masters</a> or <a data-toggle="tooltip" data-original-title="{{site.data.concepts.sparta_data_mine}}">Sparta</a>. Those are two <a data-toggle="tooltip" data-original-title="{{site.data.data_mine.data_mine}}">data mines<a/> shipping with the system. The label continues with the name of the corresponding <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_exchange}}">exchange</a> and <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market}}">market</a>.

The system ran all of the Masters task managers when it was first started.

**5. If your machine is coping well** with the processes running, you may want to run all of the Sparta task managers. To do that, select *Run All Tasks* on the menu.

**6. If your machine is getting slow or unresponsive**, you may want to stop the task managers of the exchange or markets that you are the least interested on. To do that, select *Stop All Tasks* on the menu.

{% include image.html file='how-to/data-mining-01.gif' url='yes' max-width='100' caption='To start or stop all tasks on a task managers, click the corresponding button on the menu.' %}