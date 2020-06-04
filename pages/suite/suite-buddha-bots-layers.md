---
title:  Buddha Data Mine Bots
summary: "The Buddha data mine offers Candle Patterns recognition."
sidebar: suite_sidebar
permalink: suite-buddha-bots-layers.html
---

{% include note.html content="The objective of this section is to give the basic guidelines so that the user understands what the graphic interface represents. To know how these indicators have been constructed and to learn how to use them from within the strategies, see the [Buddha Indicators](suite-buddha-indicators.html) page." %}

### Candle Patterns

To identify candle patterns on the charts, each particular candle should first be defined, grouped and parameterized, which we will call "Basic Candles". From there we can detect more complex patterns, which can be made up of one or more candles. For this reason, the "Candle Patterns" indicator has a layer for basic candles and a layer for each group of patterns.

> NOTE: <em>In the same way as any indicator, the candlestick patterns would be anticipating a possible scenario of the future conditions of the price of an asset. However, it is necessary to be very cautious and strategist in its use, since in itself, the appearance of a certain pattern is not necessarily a signal to buy or sell. Its appearance is only part of what can be a complete trading strategy and, therefore, the final result will depend on the context of the market analyzed as a whole, and in many cases complementing its use with other indicators.
Because the candlestick patterns are analyzed visually and in a very subjective way, the final result will depend on the criteria that each trader uses. This makes it a great challenge to translate this hundreds-year-old tool into a programming code, so it is necessary to first understand very well each concept that is used in this analysis to be able to parameterize it.</em>


#### Basic Candles

The starting point to search for candle patterns is to establish a standard criterion that names each candle that appears on the chart. Because they are made up of four prices, they can give rise to a large number of possible combinations. This means that there can be candles without shadows or with only one, small or large shadows. The same happens with the body and in turn with the size relationship between the body and the shadows.

When activating the "Basic Candles" layer, the corresponding panel and three colored lines can be seen on the chart:

{% include image.html file='buddha/candle-patterns/buddha-bots-layers-00-basic-candles.gif' url='yes' max-width='100' caption='"Basic Candles" - Layer.' %}

In the panel located in the upper central part of the chart, you can see the name of each basic candle and its particularities as the cursor moves over them.
Both light blue lines represent the average of the total candle lengths. The orange line is a percentage (sizeFactor) of that average, which is user-defined, below which are short candles and above which are long candles.

The following pattern properties appear in the Panel:

| Indicator Properties | Brief Description |
| :---: | :--- |
| Name | The name of the Basic Candle. |
| Size | Indicates relative size of the candle: "Short" or "Long". |
| Upper Shadow % | The percentage that the Upper Shadow covers in the total length of<br> the candle. |
| Body % | The percentage that the Body covers in the total length of the candle. |
| Lower Shadow % | The percentage that the Lower Shadow covers in the total length of<br> the candle. |
| Parameter: Nbodies | It is a user-configurable parameter, which indicates the number of<br> previous candles used to calculate the body average. |
| Parameter: dojiFactor % | It is a user-configurable parameter, which indicates when a candle is<br> a doji type based on the percentage that its body occupies in the total<br> length of the candle. |
| Parameter: sizeFactor % |It is a user-configurable parameter, which indicates the percentage of<br> the average of the total candle length used to know if a candle is<br> "Short" or "Long" (orange line in the chart). |
| Parameter: Nlengths | It is a user-configurable parameter, which indicates the number of<br> previous candles used to calculate the average of the lengths. |
| Average Size Method | It is a user-configurable parameter, which indicates the method used<br> to calculate the average of the total lengths of previous candles. |


#### One-Candle Patterns

The "One-Candle Patterns" are built from a single Basic Candle, which is in a certain market context that may indicate a possible increase or decrease in price. As with all candlestick patterns, it is not a prediction of the future price per se, but its prediction must be confirmed with the judgment of the successive candles.

{% include image.html file='buddha/candle-patterns/buddha-bots-layers-01-one-candle-patterns.gif' url='yes' max-width='100' caption='"One-Candle Patterns" - Layer.' %}

When activating the layer, the corresponding panel and a dark line can be seen on the chart.

The following pattern properties appear in the Panel:

| Indicator Properties | Brief Description |
| :---: | :--- |
| Pattern Name | Is the name of the pattern. |
| Trend Direction | The market trend during which the pattern has formed. |
| Forecast | It is the possible future scenario that represents the formation of this pattern. |
| Trend Line Method | It is the method used to calculate the moving average that represents the trend line. |
| Trend Line Period | It is the period used to calculate the moving average that represents the trend line. |
| Trend Line Value | It is the current value of the moving average that represents the trend line. |

The dark line indicates the market trend, which consists of a moving average.

The green and red arrows below and above the candles indicate the position in which the pattern appears. If the candle is green pointing up, it indicates a "Bullish Reversal" or "Bullish Continuation" forecast. If the candle is red pointing down, it indicates a "Bearish Reversal" or "Bearish Continuation" forecast.

#### Two-Candles Patterns

The "Two-Candles Patterns" are built from two Basic Candles. The other details are identical to "One-Candle Patterns"

{% include image.html file='buddha/candle-patterns/buddha-bots-layers-02-two-candles-patterns.gif' url='yes' max-width='100' caption='"Two-Candles Patterns" - Layer.' %}

When analyzing patterns of more than one candle, it is important to understand the following concepts:

<ol>
<li>The first candle in the pattern is the first candle that is chronologically formed, and so on for the following candles.</li>
<li>The first candle of the pattern is the one that defines the trend of the pattern, for this reason the value and the direction of the trend line of the pattern corresponding to the trend line of the first candle.</li>
<li>The arrow is drawn on the last candle that forms the pattern.</li>
</ol>

>NOTE: The concepts mentioned for "Two-Candles Patterns" apply to all patterns of more than one candle.

#### Three-Candles Patterns

The "Three-Candles Patterns" are built from three Basic Candles. The other details are identical to "One-Candle Patterns" and "Two-Candles Patterns".

{% include image.html file='buddha/candle-patterns/buddha-bots-layers-03-three-candles-patterns.gif' url='yes' max-width='100' caption='"Three-Candles Patterns" - Layer.' %}
