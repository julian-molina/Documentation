---
title:  Masters Data Mine Bots
summary: "The Masters data mine offers candles, volumes, candle stairs patterns, volume stairs patterns, Bollinger bands (BB), percentage bandwidth (%B), Bollinger channels, and Bollinger sub-channels."
sidebar: suite_sidebar
permalink: suite-masters-bots-layers.html
---

{% include note.html content="To learn to use these products from within strategies, see the [Masters Indicators](suite-masters-indicators.html) page." %}

## Candles

Typical candlesticks.

{% include image.html file='interface/masters-bots-layers-00-candles.gif' url='yes' max-width='100' caption='Candlesticks.' %}

## Volumes

We innovated a bit placing the buy volume at the bottom (in green), and the sell volume at the top (in red).

{% include image.html file='interface/masters-bots-layers-01-volumes.gif' url='yes' max-width='100' caption='Volume.' %}

## Candle Stairs Patterns

This is an unusual pattern proving any dataset may be plotted on the charts (and by extension, that anything can be added to the system). A Stair Pattern is defined as a set of candles going in the same direction, either up or down. You can think of these patterns as "Candle Channels", as they represent channels with an up or down direction based on underlying candles direction.

{% include image.html file='interface/masters-bots-layers-02-candle-pattern-stairs.gif' url='yes' max-width='100' caption='A simple pattern forming ascending or descending stairs.' %}

## Volume Stairs Patterns

A similar concept, this time with volumes. Whenever a sequence of volume bars is found where each one is bigger than the previous one, they are bundled together in a "Stair". The same applies when they are going down (the next is smaller than the previous one). For a trading bot, this serves to identify if sell or buy volumes are rising or declining.

{% include image.html file='interface/masters-bots-layers-03-volume-pattern-stairs.gif' url='yes' max-width='100' caption='A simple pattern forming ascending or descending stairs.' %}

## Bollinger Bands

This is the traditional <a href="https://www.bollingerbands.com/" rel="nofollow" rel="noopener" target="_blank">Bollinger Bands</a> indicator. Bollinger Bands have a moving average, in our case calculated with the last 20 periods (the line in the middle of the bands). We are plotting the moving average with one color when it is going up, and with a different color when it's going down. The upper band is at 2 Standard Deviations from the moving average, pretty much like the lower band, also at 2 Standard Deviations. These are the most widely used Bollinger Bands settings.

{% include image.html file='interface/masters-bots-layers-04-bollinger-bands.gif' url='yes' max-width='100' caption='Bollinger Bands with standard settings.' %}

## Percentage Bandwidth

This is a well-known indicator that derives from the Bollinger Bands. In a nutshell, it tells you how close the price is either to the upper band or the lower band at any point in time. When the price is in the middle of the bands (it is calculated with the close value of each candle), then %B is in the middle of its chart, at value 50. When the price touches the upper band, then %B is at 100, and finally when the price is at the lower band, then %B is at 0. 

{% include image.html file='interface/masters-bots-layers-05-percentage-bandwidth.gif' url='yes' max-width='100' caption='Percentage Bandwidth with standard settings.' %}

The chart features lines at %B values 30 and 70 since those are the most common values for traders to forecast when a reversal may happen. In our chart, %B is the one represented at #1. We've found useful to add a moving average to smooth volatility a bit and to be able to ask—at any time—if it is going up or down. The moving average calculated with the last 5 %B values is plotted as line #2. Finally, we've also added a property called Bandwidth, which represents the separation of the upper band from the lower band. It is a measure of volatility and is plotted at #3.  

{% include image.html file='interface/masters-bots-layers-06-percentage-bandwidth-2.gif' url='yes' max-width='100' caption='Percentage Bandwidth with standard settings.' %}

## Bollinger Channels

This is a non-standard indicator derived from the Bollinger Bands. These types of channels are calculated using the Bollinger Bands moving average. Essentially an upward channel begins when the moving average changes _direction_ from going down to going up, and the channel finishes when it turns from going up to down. A downward channel starts when the Bollinger Band moving average turns from going up to down, and it finishes when it starts going up again. Upward channels are plotted in green, while downward channels in red. Additional information can be found at the indicator's panel, like the number of periods contained at the channel.

{% include image.html file='interface/masters-bots-layers-07-bollinger-channels.gif' url='yes' max-width='100' caption='Bollinger Channels.' %}

## Bollinger Sub-Channels

If we consider that one Bollinger Channel can have sub-channels in the same direction (up or down) but different slopes, then we get to the concept of Bollinger Sub-Channels. The most important property of a sub-channel is its slope. The possible values are Side, Gentle, Medium, High and Extreme. With this information, a trading bot could easily ask if it is in a sub-channel with a certain slope and for how many periods. The slope or inclination of the moving average may be an indication of momentum.

{% include image.html file='interface/masters-bots-layers-08-bollinger-subchannels.gif' url='yes' max-width='100' caption='Bollinger Sub-Channels.' %}
