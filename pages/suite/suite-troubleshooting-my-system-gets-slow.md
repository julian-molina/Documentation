---
title:  My System Gets Slow
summary: "Understand how the system uses the available hardware so that you may implement workarounds and best practices."
sidebar: suite_sidebar
permalink: suite-troubleshooting-my-system-gets-slow.html
---

Dynamically rendering all the visual features in the system puts a significant load on the machine's graphics processing unit (GPU). Running multiple tasks at the same time is demanding on the central processing unit (CPU). Depending on your machine's capacity, this may result in the system getting slow and sometimes even unresponsive.

If you experience such symptoms, there are several workarounds you may implement to mitigate them.

{% include note.html content="Learn about the [system requirements](suite-system-requirements.html) to better understand what to expect in terms of the performance of your hardware." %}

## Stop Tasks That You May Not Need to Run at All Times

Data mining is a CPU-intensive activity. If you are designing a strategy, you probably don't need to have a live stream of information being processed in realtime. Learn to segment your activities and only start the tasks that you need for the work you are doing.

## Open either the design space or the charting space

Leaving the slider halfway up or down the screen causes both the design space and the charting space to consume resources. Make sure the slider is either fully up or down.

{% include /reuse/switch-from-charting-space-to-design-space.md content="more" extended="no" more="yes" %}

## Display Less Data on the Charts

Make sure you set the time scale to manual mode and adjust it so that fewer candles are displayed on the screen. Try switching the time frame box to the higher time frames so that candle density decreases.

You may also want to switch off the layers you may not be using. Remember, every piece of graphical information you see on the screen represents data your system is reading from your disk and processing to display in a graphical form.

{% include /charting_space/time-scale.md heading="" icon="no" adding="" configuring="" charts="####" content="no" definition="no" table="no" more="yes"%}

{% include /charting_space/time-frame-scale.md heading="" icon="no" adding="" configuring="" charts="####" content="no" definition="no" table="no" more="yes"%}

## Close Unused Hierarchies

The physics that govern nodes in the design space help structures of nodes to self-organize. This comes at a cost in terms of GPU processing power.

Make sure all hierarchies you are not using are collapsed.

You may also want to close any of the structures of nodes that you may not be using within the hierarchy that you may need to expand.

{% include important.html content="If these workarounds do not solve your problem and you often experience slowness or unresponsiveness when using your computer, you may want to consider upgrading your equipment. You shouldn't risk your capital with an insufficient trading infrastructure." %}