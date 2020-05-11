---
title:  There Are No Candles on The Charts
summary: "It takes time for your data mining operation to download data from the exchange and process the raw data to build candles. Check the progress of your data mining operation in the network hierarchy."
sidebar: suite_sidebar
permalink: suite-troubleshooting-there-are-no-candles-on-the-charts.html
---

There are a few reasons why you may be having issues finding candles on the charts. Please, consider the following...

## Check the Progress of the Data Mining Operation

If you are just getting started with Superalgos, still following the getting started guide, bear in mind it takes time for data to be downloaded from the exchange. Depending on the power of your hardware and the speed of your internet connection, it may take anything from half an hour to several hours to see the first few candles, particularly those of the Binance exchange, as the market spans back to September 2017.

Check the data mining operation on the network hierarchy. You will be able to see candles on the screen only after the OCHLV Sensor Bot and the Candles Volumes indicator in the Masters task manager of the corresponding exchange tasks node and market have both reached 100% progress.

{% include tip.html content="If you are not sure what the above paragraph refers to, please carefully read the instructions on [Step 6](suite-step-6.html) of the getting started guide, or watch the second video in the [video tutorial series](index.html#video-tutorial-series) as a refresher." %}

## Check the Time, Rate and Time Frame Scales

It may happen that you attempted to manipulate the charts and something went wrong in the process.

Try setting the time frame scale to 24 hours, and both the time scale and rate scale to automatic mode. Setting the time scale to automatic mode brings the whole span of the market in focus on the chart. Setting the rate scale to automatic mode sets the scale to fit the entire range of prices in the market. The goal is to make sure that all scales are set in a way in which&mdash;if there is any data to show&mdash;it will show.

If you don't know how to do that, please watch the third video in the [video tutorial series](index.html#video-tutorial-series) as a refresher, or use the below links to read about the time and rate scales.

{% include /charting_space/time-scale.md heading="" icon="no" adding="" configuring="" charts="####" content="no" definition="no" table="no" more="yes"%}

{% include /charting_space/time-frame-scale.md heading="" icon="no" adding="" configuring="" charts="####" content="no" definition="no" table="no" more="yes"%}

## Check the Integrity of the Data

Your PC may have been forcefully shut down or you may have closed the console running the Superalgos backend while running a data-mining operation. Such situations may cause some data to become corrupt.

If you are technical enough, you may want to review the latest files in the Candles Volumes indicator of the Masters Data Mine located deep in ```Multi-Period-Daily``` and ```Multi-Period-Market``` folders under ```Data-Storage > Exchange > Market > Masters > Candles-Volumes > Output > Candles```.

If you find any ```.tmp``` files or you can't open any of the ```.json``` files in a regular text editor, chances are the files are corrupt. You may try renaming the ```.tmp``` files back to ```.json```. If nothing seems to work, ask for help in the Community.

Bear in mind that, likely, the easier solution is to delete the Candle-Volumes folder and run the data mining operation again to recalculate all candles.

## Check for Errors at the Browser Level

Open Chrome's DevTools with the <kbd>F12</kbd> key (when the browser is in focus) and click the Console tab, then go back and reproduce the issue trying to show the candles on the chart. The console may display errors that are not important. Pay attention if you find errors that refer to files that can not be loaded, or similar issues.
 
{% include image.html file='how-to/report-a-bug-01.png' url='yes' max-width='100' caption='Open Developer Tools and check the console tab for potential errors.' %}

If nothing else has worked for you, then record a quick WEBM video of the problem in the charts and ask for help in the <a href="https://t.me/superalgoscommunity" rel="nofollow" rel="noopener" target="_blank">Community Telegram</a>, thoughtfully describing the issue you are experiencing and what you have done to troubleshoot it.

{% include /reuse/screen-capture-and-sharing.md content="more" extended="no" more="yes" %}