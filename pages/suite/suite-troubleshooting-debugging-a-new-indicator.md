---
title:  Debbuging a New Indicator
summary: "A case study for developers on how to debug an indicator-in-the-making. These are a few notes taken during a real issue when building the RSI indicator."
sidebar: suite_sidebar
permalink: suite-troubleshooting-debugging-a-new-indicator.html
toc: false
---

## My indicator is not running!

This is the logical checklist in such scenario:

1. Make sure all dependencies are running.

1. Determine which process is not running (Multi-Period-Daily or Multi-Period-Market).

1. Check if the corresponding execution started event is referencing the proper process. Make sure the referenced process is running without error, at 100%.

1. Check if data dependency references are in place. Make sure these dependencies are running without error, at 100%.

1. Stop all bots and delete the ```Log-Files``` folder so that you may easily identify current logs.

1. Run your indicator's dependencies.

1. Make sure they are running properly, without errors. Check the logs if in doubt.

1. Run your indicator. Check your indicator's log files.


## My indicator starts running but then stops

That is likely a sympthom of errors in the code...

{% include image.html file='troubleshooting/RSI-00.jpg' url='yes' max-width='100' caption='Pay attention to the console window and isolate the error message. In this case we have a syntax error.' %}

{% include image.html file='troubleshooting/RSI-01.jpg' url='yes' max-width='100' caption='Bring back the loop code to a proper editor to find the culprit.' %}

{% include image.html file='troubleshooting/RSI-02.jpg' url='yes' max-width='100' caption="Next error, a property we are trying to read is undefined. The console shows the number of the offending line: 28." %}

{% include image.html file='troubleshooting/RSI-03.jpg' url='yes' max-width='100' caption='Line 28 shows two potential uses of the close property: with the current record and with the previous record. It is to be expected that record.previous will be undefined starting the array.' %}

{% include image.html file='troubleshooting/RSI-04.jpg' url='yes' max-width='100' caption='We handle the particular case by running the code only when the property is not undefined.' %}

{% include image.html file='troubleshooting/RSI-05.jpg' url='yes' max-width='100' caption='Next error.' %}

{% include image.html file='troubleshooting/RSI-06.jpg' url='yes' max-width='100' caption='And the fix.' %}

{% include image.html file='troubleshooting/RSI-07.jpg' url='yes' max-width='100' caption='Now it finally run. We check the data file and see if everything looks OK at a first glance. No! The third field of the first record is undefined. So we keep debugging until we get the proper results.' %}