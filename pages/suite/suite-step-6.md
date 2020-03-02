---
title:  Monitor Data Mining Progress
summary: The system started pulling data from exchanges the minute you ran it the first time. Read on to learn the details.
sidebar: suite_sidebar
permalink: suite-step-6.html
toc: false
---

Superalgos puts you in control of the market data you will work with. To do that, the system uses a <a data-toggle="tooltip" data-original-title="{{site.data.concepts.sensor_bot}}">sensor bot</a> to pull 1-minute-candles data from exchanges and store it in your machine (it is also possible to pull raw trades data). As the data starts building up, the system uses <a data-toggle="tooltip" data-original-title="{{site.data.concepts.indicator_bot}}">indicator bots</a> to process the raw data into more elaborate <a data-toggle="tooltip" data-original-title="{{site.data.concepts.dataset}}">datasets</a> in the form of candles for all time frames, and all sorts of indicators.

The sensor bot fetches data starting from a configurable date. Once it reaches the present time, it continues connecting to the exchange once per minute, pulling data in a live stream. Indicators process data similarly and keep all your data up to date.

Depending on how you intend to use Superalgos, you may want to pull data from as far back as exchanges are willing to give. Such may be the case if you wish to backtest strategies.

On the other hand, if your interest lies in monitoring markets starting from the present time, then you most likely do not need historical data stretching that far in the past.

{% include important.html content="As mentioned earlier, for your convenience, the system starts pulling data from exchanges as soon as you start it the first time. The current default is pulling the complete BTC/USDT and ETH/USDT markets from Binance, and one-year worth of the same markets from Bitfinex (limited by the exchange). At the same time, several basic indicators are fired up. The following instructions teach you how to monitor the progress of the data mining operation. At a later time, you will learn how to work with other exchanges." %}

## Start Here

**1. Open the design space** by pulling the slider to the top of the screen.

**2. Go to the <a data-toggle="tooltip" data-original-title="{{site.data.network.network}}">network hierarchy</a>**. 

{% include /how_to/find-a-hierarchy.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**3. Hover the mouse over the network <a data-toggle="tooltip" data-original-title="{{site.data.concepts.node}}">node</a>** and click the {% include inline_image.html file="icons/12-expand.png" %} button on the menu. This action expands the <a data-toggle="tooltip" data-original-title="{{site.data.concepts.hierarchy}}">hierarchy</a>.

**4. Follow the <a data-toggle="tooltip" data-original-title="{{site.data.concepts.structure_of_nodes}}">structure of nodes</a> until you find the <a data-toggle="tooltip" data-original-title="{{site.data.network.data_mining}}">data mining</a> node**. Notice the sign below the <a data-toggle="tooltip" data-original-title="{{site.data.concepts.node}}">node</a> indicating how many <a data-toggle="tooltip" data-original-title="{{site.data.network.task_manager}}">task managers</a> are running.

{% include image.html file='how-to/data-mining-00.gif' url='yes' max-width='100' caption='The image illustrates points 1 to 6, showing the path to find the data mining node, the indication of how many task managers and tasks are running, and the progress of the sensor bot within a task.' %}

**5. Expand the data mining node**. Notice that each task manager has a label that starts with the words <a data-toggle="tooltip" data-original-title="{{site.data.concepts.masters_data_mine}}">Masters</a> or <a data-toggle="tooltip" data-original-title="{{site.data.concepts.sparta_data_mine}}">Sparta</a>. Those are two <a data-toggle="tooltip" data-original-title="{{site.data.data_mine.data_mine}}">data mines<a/> shipping with the system. The label continues with the name of the corresponding <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_exchange}}">exchange</a> and <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market}}">market</a>.

Also, notice the sign below each task manager indicating how many <a data-toggle="tooltip" data-original-title="{{site.data.network.task}}">tasks</a> are running. Notice also that the Sparta task managers are not running.

**6. Expand one of the Masters task managers**. Notice how each task controls either an <a data-toggle="tooltip" data-original-title="{{site.data.network.indicator_bot_instance}}">indicator bot instance</a> or a <a data-toggle="tooltip" data-original-title="{{site.data.network.sensor_bot_instance}}">sensor bot instance</a>. 

Also, notice the indication of progress below the sensor bot instance node. The message includes the activity the bot is performing, the exchange and market concerned, and the date that was last processed. Each of the Masters task managers has a similar configuration, but the indicators and sensors within work in different exchange/market combinations.

Indicators, on the other hand, do not show their progress on the design space. However, you may see the last date they processed on the console.

{% include image.html file='how-to/data-mining-04.png' url='yes' max-width='100' caption='Indicator bots show the last datetime processed in the last column of the console logs.' %}

{% include note.html content="Some bots do not yet show the progress on the console, as they are pending an update." %}