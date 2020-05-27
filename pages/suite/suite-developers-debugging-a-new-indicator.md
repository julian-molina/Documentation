---
title:  Debugging a New Indicator
summary: "A case study for developers on how to debug an indicator-in-the-making. These are a few notes taken during a real issue when building the RSI indicator."
sidebar: suite_sidebar
permalink: suite-developers-debugging-a-new-indicator.html
toc: false
---

## My Indicator Is Not Running!

This is the logical checklist in such scenario:

1. Make sure all dependencies are running.

1. Determine which process is not running (Multi-Period-Daily or Multi-Period-Market).

1. Check if the corresponding execution started event is referencing the proper process. Make sure the referenced process is running without error, at 100%.

1. Check if data dependency references are in place. Make sure these dependencies are running without error, at 100%.

1. Stop all bots and delete the ```Log-Files``` folder so that you may easily identify current logs.

1. Run your indicator's dependencies.

1. Make sure they are running properly, without errors. Check the logs if in doubt.

1. Run your indicator. Check your indicator's log files.


## My Indicator Runs With Errors

You may debug an indicator by [debugging the task](suite-developers-debugging-a-task.html) it runs under.

