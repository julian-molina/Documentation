---
title:  Buddha indicators
summary: "A set of indicators built in the Buddha data mine including Candle Patterns recognition"
sidebar: suite_sidebar
permalink: suite-buddha-indicators.html
---

{% include note.html content="The following indicators are available under the Buddha task managers in the data mining section of the network hierarchy." %}

## Candle Patterns

### Introduction

If you are one of the lovers of candle patterns, you have come to the right place! As is well known, this is a very useful and versatile tool that traders use to visually determine the general sentiment of market participants. Japanese candle theory is well known and is fully available on the internet, so what has been done here is to order the information so that it can be written in easily parameterizable programming code. In the following sections, only the basic concepts will be described to understand the logical sequence of reasoning that has been used to write the computer code, and in this way be able to modify it and adapt it to each particular need.
For its correct interpretation and use, it is recommended to deepen the ideas and concepts by reading the following books:

* "Candlestick Charting Explained" - Author: Greg Morris
* “Technical Analysis of The Financial Markets” - Author: John J. Murphy
* “Encyclopedia of Candlestick Charts” - Author: Thomas N. Bulkowski
* “Encyclopedia of Chart Patterns” - Author: Thomas N. Bulkowski
* “Japanese Candlestick Charting Techniques” - Author: Steve Nison

and also visit the following websites:

* <a href="http://thepatternsite.com/" rel="nofollow" rel="noopener" target="blank">Thomas Bulkowski: ThePatternSite.com</a>
* <a href="https://www.investopedia.com/articles/technical/112601.asp" rel="nofollow" rel="noopener" target="blank">Investopedia: Introduction to Technical Analysis Price Patterns</a>
* <a href="https://www.candlesticker.com/" rel="nofollow" rel="noopener" target="blank">CandleSticker by American Bulls</a>

The advantages of using bots to recognize patterns are the following: they are objective, they do not have feelings or impulses, they can analyze thousands of possibilities and combinations in a few minutes, and another very interesting aspect is that they allow us to play with the settings to do all kinds of tests as many times as we want.

With the results obtained, we will be able to make statistics to adjust the patterns to the crypto world, improving its efficiency and why not, create new and innovative patterns that are written in this story that is just beginning.

**Welcome to the wonderful and mysterious world of Japanese Crypto-Candles!!**

### Parts of a Candle

Surfing the internet you can find hundreds of candle schemes, in which the parts that form it are mentioned, differing a little on some occasions. For this reason, we will limit ourselves here only to indicating what name we adopt for each part of the candle.

The first price from which the candle begins to form is called the **"Open Price"**. The last price from which the candle finishes forming is called **"Close Price"**. The distance between both prices is called **"Body"**. A very interesting fact is that market volatility can cause the price to fluctuate beyond both prices during candle formation. With which the "Shadows" are added to the candle. The **"Upper Shadow"** is the one that links the **“Max Price”** that has been reached with the upper body. The **"Lower Shadow"** is the one that links the **“Min Price”** that has been reached with the lower body.

Regarding color, the following criteria have been adopted in Superalgos:
* When the closing price is higher than the opening price, the body of the candle is painted <span style="color:green">**green**</span>. This indicates that it is a **"Bullish"** candle.
* When the closing price is less than the opening price, the body of the candle is painted <span style="color:red">**red**</span>. This indicates that it is a **"Bearish"** candle.

###  Body of Doji Candles
Japanese candle theory defines a doji candle as one in which the closing price equals the opening price. In other words, a doji candle should not have a body. This is in theory, but in practice, the following aspects arise to take into account:

* Price volatility
* The precision with which prices are recorded

This makes it very unlikely that both prices match exactly and there is always a body even if it is very small, making it appear at first glance on the chart that the body is non-existent.
For this reason, we must define a range of uncertainty in body length to determine whether a candle is a doji or not.
We are going to assume by default that the doji body may be less or equal to 3% of the total length of the candle.
This value called “dojiFactor” inside the program code can be changed by the users.

### Relative Size: Short or Long

It is very important to understand this concept since during the study and identification of candle patterns you must differentiate the size of each particular candle, that is, which ones are long and which are short. At first glance, this seems very simple, but when having to translate it into an algorithm, you have to define what tools will be used and how they will be parameterized.

To start, we need to establish some reference to decide what is long and what is short, since a long candle in some market context may be short in another context. An important aspect is that when we look at a chart, our view can deceive us since the context around a candle involves past and future candles, which by backtesting this is totally feasible, but in practice, when our algorithm is working on live trading, it can only know the past of each new candle that is formed.

Thus, from this logical reasoning, it can be deduced that the average of the size of the past candles, limited to a certain number of candles, must be used as a frame of reference. Basically, this method arises from common sense and therefore it is the one observed widely used in the literature. Some authors differ in their criteria averaging only the bodies or averaging the total lengths including also the shadows.

For this reason, what has been done is to make both criteria available:

* **Body average:** Bulkowski uses this criterion to detect candles of the type: "Long Green Candle" and "Long Red Candle". Since they are a particular case that occurs when the size of the body extends more than three times compared to the previous candle's body average.

* **Length average:** this criterion is used in a general way for all basic candles since it also includes Doji candles, which have no body (or have very small bodies) and with the previous criterion they would always be sized as "Short", which is not what we are looking for.

><em> NOTE: Although these are just some techniques that can be used, thanks to the flexibility that Superalgos has given us, we can create and adapt any other idea that occurs to us to determine when a candle is long or when it is short. </em>


### Basic Candles Families

Below is the list of basic candles. They are grouped by families since they have certain characteristics in common.

><em> NOTE: Generally in the literature white and black are used in the names of the candles, indicating if they are bullish or bearish respectively. Thus, white has been changed to green and black to red.</em>

#### Classic Candles

These candles have the following characteristics in common:

1. Both shadows are present.
2. Each shadow is shorter than the body.
3. The opening price differs from the closing price.

According to their particular characteristics, they are named as follows:

| Representation | Basic Candle Name  | Particular Characteristics |
| :---: | :--- | :--- |
| ![Short-Candle](images/buddha/candle-patterns/short-candle.png) | <br> **"Short Green Candle"** <br> **"Short Red Candle"** | <br> 1) Bullish or Bearish. <br> 2) Relative Size: Short.|
| ![Candle](images/buddha/candle-patterns/candle.png) | <br> **"Green Candle"** <br> **"Red Candle"** | <br> 1) Bullish or Bearish. <br> 2) Relative Size: Long.  |
| ![Long-Candle](images/buddha/candle-patterns/long-candle.png) | <br> **"Long Green Candle"** <br> **"Long Red Candle"** |<br> 1) Bullish or Bearish. <br> 2) The body is at least three times higher<br> than the average of the previous bodies. <br> 3) Relative Size: Long. |

#### Marubozu Candles

These candles have the following characteristics in common:

1. Lack of at least one shadow.
2. If it has one shadow, it must be shorter than the body.
3. The opening price differs from the closing price.
4. Relative Size: Short or Long.

According to their particular characteristics, they are named as follows:

| Representation | Basic Candle Name | Particular Characteristics |
| :---: | :--- | :--- |
| ![Marubozu](images/buddha/candle-patterns/marubozu.png) | <br> **"Green Marubozu"** <br> **"Red Marubozu"** | <br> 1) Bullish or Bearish. <br> 2) No shadows. |
| ![Opening-Green-Marubozu](images/buddha/candle-patterns/opening-green-marubozu.png) | <br> **"Opening Green Marubozu"** | <br> 1) Bullish. <br> 2) No lower shadow. |
| ![Closing-Green-Marubozu](images/buddha/candle-patterns/closing-green-marubozu.png) | <br> **"Closing Green Marubozu"**  | <br> 1) Bullish. <br> 2) No upper shadow. |
| ![Opening-Red-Marubozu](images/buddha/candle-patterns/opening-red-marubozu.png) | <br> **"Opening Red Marubozu"** |<br> 1) Bearish. <br> 2) No upper shadow. |
| ![Closing-Red-Marubozu](images/buddha/candle-patterns/closing-red-marubozu.png) | <br> **"Closing Red Marubozu"** |<br> 1) Bearish. <br> 2) No lower shadow. |

#### Spinning Top Candles

These candles have the following characteristics in common:

1. Have at least one shadow.
2. At least one shadow is greater than the body.
3. The opening price differs from the closing price.

According to their particular characteristics, they are named as follows:

| Representation | Basic Candle Name | Particular Characteristics |
| :---: | :--- | :--- |
| ![Spinning-Top](images/buddha/candle-patterns/spinning-top.png) | <br> **"Green Spinning Top"** <br> **"Red Spinning Top"** | <br> 1) Bullish or Bearish. <br> 2) Relative Size: Short or Long. <br> 3) If it's relative size is long, none of the shadows<br> can exceed three times the body. |
| ![High-Wave](images/buddha/candle-patterns/high-wave.png) | <br> **"High Wave"** |<obr> 1) Bullish or Bearish. <br> 2) Relative Size: Long. <br> 3) The length of at least one shadow is at least<br> 3 times larger than the body. |

#### Doji Candles

These candles have the following characteristics in common:

1. Have no body, or very small body if it is allowed.

According to their particular characteristics, they are named as follows:

| Representation | Basic Candle Name | Particular Characteristics |
| :---: | :--- | :--- |
| ![Four-Price-Doji](images/buddha/candle-patterns/four-price-doji.png) | <br> **"Four-Price Doji"** | <br> 1) No shadows. <br> 2) Relative Size: Short. |
| ![Star-Doji](images/buddha/candle-patterns/star-doji.png) | <br> **"Star Doji"** | <br> 1) The body is located nearly mid-range<br> (between 60% and 40% of total length). <br> 2) Relative Size: Short. |
| ![Long-Legged-Doji](images/buddha/candle-patterns/long-legged-doji.png) | <br> **"Long-Legged Doji"** | <br> 1) The body is located nearly mid-range<br> (between 60% and 40% of total length). <br> 2) Relative Size: Long. |
| ![Dragonfly-Doji](images/buddha/candle-patterns/dragonfly-doji.png) | <br> **"Dragonfly Doji"** | <br> 1) Upper shadow shorter than 1% of total candle length. <br> 2) Relative Size: Long. |
| ![Gravestone-Doji](images/buddha/candle-patterns/gravestone-doji.png) | <br> **"Gravestone Doji"** | <br> 1) Lower shadow shorter than 1% of total candle length. <br> 2) Relative Size: Long. |
| ![Generic-Doji](images/buddha/candle-patterns/generic-doji.png) | <br> **"Generic Doji"** | <br> All doji candles that do not match the 5 mentioned above. |

><em>NOTE: It is important to know that these definitions of candles are those that appear in the general literature. But for us, they are only the initial kick to start, since the idea is to expand knowledge collaboratively and translate it into code. What is meant is that we are not limited only to what is popularly used, we can easily create new types of candles and immediately test their efficiency.</em>


### Pattern Validation

To find candle patterns on the chart, it is necessary to analyze the market context in which the basic candles appear and how they are related to each other. For this reason, the following concepts are necessary:

1. **Trend Line:**
To determine if prices are in an "Uptrend" or a "Downtrend", a reference trend line is necessary, which is generally a moving average.
2. **Minimum Trend Candles:**
It is the minimum number of candles that must be on the same trend line to validate a pattern. By default, 3 candles will be used.
3. **Forecast:**
  * *Bullish Reversal:* In a downtrend, a pattern is considered as valid when body of first pattern's candle is below the trend line.
  * *Bullish Continuation:* In an uptrend, a pattern is considered as valid when at least open prices of all pattern candles are above the trend line.
  * *Bearish Reversal:* In an uptrend, a pattern is considered as valid when body of first pattern's candle is above the trend line.
  * *Bearish Continuation:* In a downtrend, a pattern is considered as valid when at least open prices of all pattern candles are below the downtrend.

### Indicator Products

| Product Name | Product Variable | Property Variables |
| :---: | :---: | :--- |
| Basic Candles | ```basicCandle``` | ```name```, ```size```, ```direction```, ```upperShadow```, ```body```,<br> ```lowerShadow```, ```length```, ```meanBody```, ```meanLength```|
| One-Candle Patterns | ```oneCandlePattern``` | ```name```, ```trend```, ```forecast```, ```trendLine```|
| Two-Candles Patterns | ```twoCandlePattern``` | ```name```, ```trend```, ```forecast```, ```trendLine``` |
| Three-Candles Patterns | ```threeCandlePattern``` | ```name```, ```trend```, ```forecast```, ```trendLine``` |

**Examples:**

1. ```chart.at24hs.basicCandle.name === "Long Green Candle"``` — Is "Long Green Candle" the name of the current basic candle?

2. ```chart.at24hs.basicCandle.upperShadow > chart.at24hs.basicCandle.body``` — Is the upper shadow longer than the body?

#### "Basic Candles" product

The following table details the variables that can be used in the codes of the conditions of the trading strategies:

| Variable | Description | Possible Values |
| :---: | :--- | :--- |
| ```name``` | The name that has been assigned<br> to the basic candle based on the<br> configuration of the four prices | ```Short Green Candle```, ```Short Red Candle```,<br> ```Green Candle```, ```Red Candle```,<br> ```Long Green Candle```, ```Long Red Candle```,<br> ```Green Marubozu```, ```Opening Green Marubozu```,<br> ```Closing Green Marubozu```, ```Red Marubozu```,<br> ```Opening Red Marubozu```, ```Closing Red Marubozu```,<br> ```Red Spinning Top```, ```Green Spinning Top```,<br> ```High Wave```, ```Four-Price Doji```,<br> ```Star Doji```, ```Long-Legged Doji```,<br> ```Dragonfly Doji```, ```Gravestone Doji```,<br> ```Generic Doji``` |
| ```size``` | The relative size of the candle | ```short```, ```long```|
| ```direction``` | Indicates if it's a bullish<br> or a bearish candle | ```bullish```, ```bearish``` |
| ```upperShadow``` | Is the length of the upper shadow |  |
| ```body``` | Is the length of the body |  |
| ```lowerShadow``` | Is the length of the lower shadow |  |
| ```length``` | Is the total length of the candle<br> (candle.max - candle.min) |  |
| ```meanBody``` | The moving average of the<br> previous candle bodies|  |
| ```meanLength``` | The moving average of the<br> previous candle lengths  |  |


The following table details the parameters that can be configured in the code of the indicator products:

| Configurable Parameter | Description | Default Value | Normal Values |
| :---: | :--- | :---: | :---: |
| ```Nbodies``` | The number of previous candle bodies<br> used to calculate "meanBody" | 10 | 5 to 20 |
| ```dojiFactor``` | It is the maximum percentage allowed that<br> the body can have with respect to length,<br> so that the candle is included in the Doji family | 3 | 0 to 5 |
| ```sizeFactor``` | It is the percentage of the "meanLength"<br> used to determinate the "size" of a candle<br> (orange line on the chart) | 75 | 60 to 80 |
| ```Nlengths``` | The number of previous candle lengths used<br> to calculate "meanLength" | 20 | 10 to 25 |
| ```sizeMethod``` | The method used to calculate "meanLength" | EMA | SMA or EMA |

To change the above mentioned parameters, open the product definition called “Basic Candles”, then open the “Java Script Code” of the “Procedure Loop”, and you will find them in the first part of the code, as you can see in the next picture:

{% include image.html file='buddha/candle-patterns/basic-candles-parameters.PNG' url='yes' max-width='100' caption='"Basic Candles" product code.' %}


#### "One-Candle Patterns" product

The following table details the variables that can be used in the conditions of the trading strategies:

| Variable | Description | Predefined Values |
| :---: | :--- | :--- |
| ```name``` | It is the name that has been assigned to<br> the pattern based on the configuration of<br> the candle that make it up | ```Bearish Strong Line```, ```Bearish Belt Hold```,<br> ```Hanging Man```, ```Shooting Star```,<br> ```Bullish Belt Hold```, ```Hammer```,<br> ```Bullish Strong Line```|
| ```trend``` | The market trend during which the pattern<br> has formed | ```Uptrend```, ```Downtrend```|
| ```forecast``` | It is the possible future scenario that<br> represents the formation of this pattern | ```Bullish Continuation```, ```Bullish Reversal```,<br> ```Bearish Continuation```, ```Bearish Reversal```|
| ```trendLine``` | The value of the Moving Average that<br> represents the trend line on which<br> the pattern was formed | |

> NOTE: "Bearish Strong Line" and "Bullish Strong Line" patterns could be both "Bearish Reversal" or "Bearish Continuation" depending on the market context.

The following table details the parameters that can be configured in the code of the indicator products:

| Parameter | Description | Default Value | Normal Values |
| :---: | :--- | :---: | :---: |
| ```N``` | It is the period of the moving average<br> used to calculate the trend line | 10 | 5 to 20 |
| ```trendMethod``` | The method used to calculate the<br> trend line Moving Average | EMA | SMA or EMA |

To change the above mentioned parameters, open the product definition called “One-Candle Patterns”, then open the “Java Script Code” of the “Procedure Loop”, and you will find them in the first part of the code, as you can see in the next picture:

{% include image.html file='buddha/candle-patterns/one-candle-patterns-parameters.PNG' url='yes' max-width='100' caption='"One-Candle Patterns" product code.' %}

#### "Two-Candles Patterns" product

The following table details the variables that can be used in the conditions of the trading strategies:

| Variable | Description | Predefined Values |
| :---: | :--- | :--- |
| ```name``` | It is the name that has been assigned to<br> the pattern based on the configuration of<br> the candles that make it up | ```Last Engulfing Bottom```, ```Bearish Engulfing```,<br> ```Bearish Harami```, ```Bearish Harami Cross```,<br> ```Bearish Tasuki Line```, ```Descending Hawk```,<br> ```Tweezers Top```, ```Two-Candle Shooting Star```,<br> ```Last Engulfing Top```, ```Bullish Engulfing```,<br> ```Bullish Harami```, ```Bullish Harami Cross```,<br> ```Bullish Tasuki Line```, ```Tweezers Bottom```|
| ```trend``` | The market trend during which the pattern<br> has formed | ```Uptrend```, ```Downtrend```|
| ```forecast``` | It is the possible future scenario that<br> represents the formation of this pattern | ```Bullish Continuation```, ```Bullish Reversal```,<br> ```Bearish Continuation```, ```Bearish Reversal```|
| ```trendLine``` | The value of the Moving Average that<br> represents the trend line on which<br> the pattern was formed | |

> NOTE: The trend line is the same as that configured in the "One-Candle Patterns" product.

#### "Three-Candles Patterns" product

The following table details the variables that can be used in the conditions of the trading strategies:

| Variable | Description | Predefined Values |
| :---: | :--- | :--- |
| ```name``` | It is the name that has been assigned to<br> the pattern based on the configuration of<br> the candles that make it up | ```Advance Block```, ```Deliberation```,<br> ```Identical Three Crows```, ```Three Inside Down```,<br> ```Three Outside Down```, ```Three Inside Up```,<br> ```Three Outside Up```|
| ```trend``` | The market trend during which the pattern<br> has formed | ```Uptrend```, ```Downtrend```|
| ```forecast``` | It is the possible future scenario that<br> represents the formation of this pattern | ```Bullish Continuation```, ```Bullish Reversal```,<br> ```Bearish Continuation```, ```Bearish Reversal```|
| ```trendLine``` | The value of the Moving Average that<br> represents the trend line on which<br> the pattern was formed | |

> NOTE: The trend line is the same as that configured in the "One-Candle Patterns" product.
