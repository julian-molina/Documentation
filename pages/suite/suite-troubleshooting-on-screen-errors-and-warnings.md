---
title:  On-Screen Errors and Warnings
summary: "When running a task or working on a strategy, errors in the session or the syntax of conditions and formulas are signaled at the offending node."
sidebar: suite_sidebar
permalink: suite-troubleshooting-on-screen-errors-and-warnings.html
toc: false
---

The frontend application marks errors by drawing a red ring around the offending node and offers a brief description of the error on-screen.

When running a trading session, the session node is usually the one featuring the error notice.

When working on a strategy, errors in the syntax or logic of conditions and formulas are displayed similarly. In such a context, make sure you turn on the *Formulas & Conditions* layer of the corresponding session and look around within your workspace. Hover the mouse pointer over the node with a red ring and you should get a description of what is that is causing the unexpected behavior.

{% include image-ext.html file='https://user-images.githubusercontent.com/13994516/63213696-b52ff500-c10f-11e9-9bc1-741ecb0858ef.gif' url='yes' max-width='100'  caption='Notice the red ring and the error notice in yellow.' %}

Bear in mind that when the slider is fully closed, errors occurring in a simulation will no longer show up in the design space, as shown in the below video:

{% include image-ext.html file='https://user-images.githubusercontent.com/13994516/63213579-528a2980-c10e-11e9-8464-76cb4b369db4.gif' url='yes' max-width='100'  caption='The slider must be partially open showing the charting space for strategy-based errors to show on-screen' %}
