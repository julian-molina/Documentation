---
title:  Alpha indicators
summary: "A set of indicators built in the Alpha data mine including Average True Range (ATR), Rate of Change (ROC), Stochastic indicators."
sidebar: suite_sidebar
permalink: suite-alpha-indicators.html
---

{% include note.html content="The following indicators are available under the Alpha task managers in the data mining section of the network hierarchy." %}

## Average True Range (ATR)

There are two products with different smoothing function avaiable, each with different period configurations:

| Product Name | Product Variable | Period Variables |
| :---: | :---: | :--- | 
| ATR - SMA | ```atrSMA``` | ```atr2```, ```atr3```, ```atr14``` |
| ATR - RMA | ```atrRMA``` | ```atr2```, ```atr3```, ```atr14``` |

**Examples:**

1. ```chart.at24hs.atrSMA.atr3 > chart.at24hs.atrSMA.atr14``` — Faster ATR (ATR-3) value above slower ATR (ATR-14) value indicates a higher volatility in short term movement?

1. ```chart.at04hs.atrRMA.atr3 > chart.at04hs.atrRMA.atr14``` — Same examples as above but with RMA (Exponatial Moving Average) as smoothing function.

## Rate of Change (ROC)

There are three products based on various periods available. As its an simple indicator it has only one value, percentage change to previous period:

| Product Name | Product Variable | Period Variables |
| :---: | :---: | :--- | 
| ROC | ```roc9``` | ```value``` |
| ROC | ```roc32``` | ```value``` |
| ROC | ```roc76``` | ```value``` |

**Examples:**

1. ```chart.at01hs.roc9.value > 0 && chart.at01hs.roc9.value > chart.at01hs.roc9.previous.value``` — Check if Rate of Change is above zero trend line and moving in upwards.

## Stochastic

Stochastic provides currently only one product with common default setting of a stochastic indicator.

| Product Setting | Product Variable | EMAs |
| :---: | :---: | :--- |
| Stochastic (14, 3, 3) | ```stoch1433``` | ```fastLine```, ```slowLine``` |

**Examples:**

1. ```chart.at04h.stoch1433.slowLine >= 80 && chart.at04h.stoch1433.fastLine < chart.at04h.stoch1433.slowLine``` — Check overbought condition and fast line lower than slow line, indicating trend reversal.
