---
title:  Masters Data Mine Bots
summary: "The Masters data mine offers candles, volumes, candle channels, volume channels, Bollinger bands (BB), Percentage Bandwidth (%B), Bollinger Channels, Bollinger Sub-Channels, and Support & Resistance."
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

## Candle Channels

A candles channel is defined as a set of candles going in the same direction, either up or down. They represent channels with an up or down direction based on underlying candles direction.

{% include image.html file='interface/masters-bots-layers-02-candle-pattern-stairs.gif' url='yes' max-width='100' caption='A simple pattern forming ascending or descending stairs.' %}

## Volume Channels

A similar concept, this time with volumes. Whenever a sequence of volume bars is found where each one is bigger than the previous one, they are bundled together in a channel. The same applies when they are going down (the next is smaller than the previous one). For a trading bot, this serves to identify if sell or buy volumes are rising or declining.

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

## Resistances & Supports &mdash; New!

This indicator is an interpretation of the concept of resistance and support levels. The indicator identifies levels (a price range) on which price is rejected, and keeps a counter of how many times rejections occur until the level is breached.

{% include image.html file='interface/support-resistance-00.PNG' url='yes' max-width='100' caption='Each relative high rejected at the level increments the counter, and changes the color of the level.' %}

Each level is determined by the reference rate, which is the rate of the first rejection. However, the level is not a specific rate, but a *rate range* expressed as a percentage of the reference rate. The percentage used to determine a level varies depending on the time frame. The smaller the time frame, the smaller the percentage.

Also, each level is calculated in different variations using different percentages to determine the rate range that makes up the level. Each of these variations in the rate range of a level is called a *zone*.

For simplicity's sake, only the first zone of each level is rendered on-screen. That is, what you see on-screen is the representation of a single variation of a level. However, strategies have access to several different versions increasing in zone sizes.

The way in which a level is visualized on screen depends on the number of rejections that have occured at the particular level since is was first established:

| Number of Rejections | Graphics | Comments |
| :---: | :---: | :--- |
| 1 | <span style="display: block; border-bottom: 1px dotted grey;">&nbsp;</span> | A faint, grey dotted line marking the reference rate of the support / resistance level. |
| 2 | <span style="display: block; background: RGB(150, 150, 150, 0.2); ">&nbsp;</span> | A grey block, marking the range of rates that make up the level. | 
| 3 | <span style="display: block; background: RGB(2, 149, 170, 0.2); ">&nbsp;</span> | A turquoise block. |
| 4 | <span style="display: block; background: RGB(244, 228, 9, 0.2); ">&nbsp;</span> | A yellow block. |
| 5 | <span style="display: block; background: RGB(188, 214, 67, 0.2); ">&nbsp;</span> | A green block. |
| 6 | <span style="display: block; background: RGB(240, 162, 2, 0.2); ">&nbsp;</span> | An orange block. |
| 7 or more | <span style="display: block; background: RGB(91,80, 122, 0.4); ">&nbsp;</span> | A purple block. |

{% include image.html file='interface/support-resistance-01.gif' url='yes' max-width='100' caption='Each relative high rejected at the level increments the counter, and changes the color of the level.' %}

Once the price breaks through the level, the level dissappears.

When a level is identified and the rejection counter is greater than zero, the level remains *"in memory"*. However, this doesn't mean that the level is graphically represented on-screen at all times. On the contrary, not all levels are represented on-screen at all times. 

The criteria to render level on-screen is influenced by the price at the current candle. For each candle, only five levels of resistance and five levels of support are rendered, above and below the price, respectively. This is to clear up the screen and limit the density of information in display when information is not relevant. As price moves up and down, some levels are hidden, some new levels may form, and pre-existing levels may emerge.

{% include image.html file='interface/support-resistance-02.gif' url='yes' max-width='100' caption='Notice the discontinuity in the level marked in blue caused by the drop of the price and the emergence of new levels below. However, despite the level stops being rendered on screen, it remains hidden and re-emerges when the price comes back up.' %}

### Panels

| Bounces | Levels | Zone Sizes | Details |
| :---: | :---: | :---: | :--- |
| ![image](images/interface/support-resistance-01-panel-bounces.png) | ![image](images/interface/support-resistance-02-panel-levels.png) | ![image](images/interface/support-resistance-03-panel-zone-sizes.png) | **Resistance / Support Bounces:** <br />The panel shows the number of bounces off each of the six zones of the first three levels.<br /><br />**Resistance / Support Levels:** <br />The panel indicates the rate on which the closest five resistance or support levels are located, and the number of periods the levels have been in existence, counting from the period of the first rejection. <br /><br />**Resistance / Support Zone Sizes:** <br /> The panel shows the sizes of the different zones tracked for each level. However, remember that only the first zone is rendered on screen. |

