---
title:  Masters indicators
summary: "A set of indicators built in the Masters data mine including candles, Bollinger Bands (BB), Percentage Bandwidth (%B), Bollinger Channels, and Bollinger Subchannels."
sidebar: suite_sidebar
permalink: suite-masters-indicators.html
---

{% include note.html content="The following indicators are available under the Masters task managers in the data mining section of the network hierarchy." %}

## Candles

The product ```candle``` features five different properties that you may use.

| Product Name | Product Variable | Property Variables |
| :---: | :---: | :--- | 
| Candles | ```candle``` | ```min```, ```max```, ```open```, ```close```, ```direction``` |

```candle.min```: The minimum price of the last closed candle (low).

```candle.max```: The maximum price of the last closed candle (high).

```candle.open```: The price at which the last closed candle opened.

```candle.close```: The price at which the last closed candle closed.

```candle.direction```: 
* ```"Down"```: candle.close < candle.open (bearish candle)
* ```"Up"```: candle.close > candle.open (bullish candle)
* ```"Side"```: candle.close = candle.open (neutral candle)

## Bollinger Bands (BB)

The product ```bollingerBand``` features four different properties that you may use.

| Product Name | Product Variable | Property Variables |
| :---: | :---: | :--- | 
| Bollinger Bands | ```bollingerBand``` | ```movingAverage```, ```standardDeviation```, ```deviation```, ```direction``` |

```bollingerBand.movingAverage```: The value of the current moving average (20 periods).

```bollingerBand.standardDeviation```: The value of current the [standard deviation](https://en.wikipedia.org/wiki/Standard_deviation).

```bollingerBand.deviation```: bollingerBand.standardDeviation * 2

```bollingerBand.direction```:  
* ```"Down"```: bollingerBand.previous.movingAverage > bollingerBand.movingAverage 
* ```"Up"```: bollingerBand.previous.movingAverage < bollingerBand.movingAverage
* ```"Side"```: bollingerBand.previous.movingAverage = bollingerBand.movingAverage)

## Percentage Bandwidth (%B)

The product ```percentageBandwidth``` features four different properties that you may use.

| Product Name | Product Variable | Property Variables |
| :---: | :---: | :--- | 
| Percentage Bandwidth | ```percentageBandwidth``` | ```value```, ```movingAverage```, ```bandwidth```, ```direction``` |

```percentageBandwidth.value```: A numeric value between 0 and 100; the current value of the percentage bandwidth.

```percentageBandwidth.movingAverage```: A numeric value between 0 and 100; the current value of the percentage bandwidth moving average.

```percentageBandwidth.bandwidth```: A numeric value between 0 and 100; the current bandwidth.

## Bollinger Channels (BC)

The product ```bollingerChannel``` features two different properties that you may use.

| Product Name | Product Variable | Property Variables |
| :---: | :---: | :--- | 
| Bollinger Channels | ```bollingerChannel``` | ```direction```, ```period``` |

```bollingerChannel.direction```: Possible values are ```"Down"```, ```"Up"```, and ```"Side"```.

```bollingerChannel.period```: The number of periods the channel spans at the moment the variable is being read. For instance, if a channel spans 10 candles and the variable is checked on the fourth candle, then _bollingerChannel.period_ = 4. Put in other words, it is the current span of the channel.

## Bollinger SubChannels (BSC)

The product ```bollingerSubChannel``` features three different properties that you may use.

| Product Name | Product Variable | Property Variables |
| :---: | :---: | :--- | 
| Bollinger SubChannels | ```bollingerSubChannel``` | ```direction```, ```period```, ```slope``` |

```bollingerSubChannel.direction```: Possible values are ```"Down"```, ```"Up"```, and ```"Side"```.

```bollingerSubChannel.period```: The number of periods the subchannel spans at the moment the variable is being read. For instance, if a subchannel spans 10 candles and the variable is checked on the fourth candle, then _bollingerChannel.period_ = 4. Put in other words, it is the current span of the subchannel.

```bollingerSubChannel.slope```: Indicates how steep the slope of the subchannel is. Possible values are ```"Side"```, ```"Gentle"```, ```"Medium"```, ```"Steep"```, ```"Extreme"``` (in order from lowest to highest).

{% include /reuse/bollinger-subchannels-calculation.md heading="" icon="no" extended="no" content="more" definition="bold" table="no" more="yes"%}

## Resistances & Supports &mdash; New!

The indicator features two data products: ```resitance``` and ```support```. 

| Product Name | Product Variable |
| :--- | :--- |
| Resistance | ```resistance``` | 
| Support | ```support``` |

| Resistance Properties | Possible Values of (i) | Comments |
| :--- | :---: | :--- |
| ```resitance(i)Rate``` | 1 to 5 | The reference rate of the level. |
| ```resistance(i)Period``` | 1 to 5 | The number of periods the level has been in existence. |
| ```resistance(i)Bounce1``` | 1 to 5 | The number of bounces for zone 1, the one rendered on-screen. |
| ```resistance(i)Bounce2``` | 1 to 3 | The number of bounces for zone 2, only available for the first three levels. Zone 2 is two times bigger than zone 1. |
| ```resistance(i)Bounce3``` | 1 to 3 | The number of bounces for zone 3, only available for the first three levels. Zone 3 is three times bigger than zone 1. |
| ```resistance(i)Bounce5``` | 1 to 3 | The number of bounces for zone 5, only available for the first three levels. Zone 5 is five times bigger than zone 1. |
| ```resistance(i)Bounce10``` | 1 to 3 | The number of bounces for zone 10, only available for the first three levels. Zone 10 is ten times bigger than zone 1. |
| ```resistance(i)BounceAll``` | 1 to 3 | The number of bounces for zone All, only available for the first three levels. Zone All is one hundred times bigger than zone 1. |

| Support Properties | Possible Values of (i) | Comments |
| :--- | :---: | :--- |
| ```support(i)Rate``` | 1 to 5 | The reference rate of the level. |
| ```support(i)Period``` | 1 to 5 | The number of periods the level has been in existence. |
| ```support(i)Bounce1``` | 1 to 5 | The number of bounces for zone 1, the one rendered on-screen. |
| ```support(i)Bounce2``` | 1 to 3 | The number of bounces for zone 2, only available for the first three levels. Zone 2 is two times bigger than zone 1. |
| ```support(i)Bounce3``` | 1 to 3 | The number of bounces for zone 3, only available for the first three levels. Zone 3 is three times bigger than zone 1. |
| ```support(i)Bounce5``` | 1 to 3 | The number of bounces for zone 5, only available for the first three levels. Zone 5 is five times bigger than zone 1. |
| ```support(i)Bounce10``` | 1 to 3 | The number of bounces for zone 10, only available for the first three levels. Zone 10 is ten times bigger than zone 1. |
| ```support(i)BounceAll``` | 1 to 3 | The number of bounces for zone All, only available for the first three levels. Zone All is one hundred times bigger than zone 1. |

**Examples:**

Let's say you wish to check if you have a strong support level below the current price on the 1H chart.

* ```chart.at01hs.support.support1Bounce1``` tells you the number of times price has bounced off the first support level; a high number of bounces may mean the level has strong support.

* ```chart.at01hs.support.support1Period``` tells you how long the support level has been "alive"; long-lasting support levels may mean the level is strong, as it hasn't been breached in a long time.

* ```chart.at01hs.candle.close - chart.at01hs.support.support1Rate``` tells you how far down the first level of support is.

Checking the first level only may not be enough. Bear in mind that the first level may show weak support, but there may be stronger support at lower levels.





