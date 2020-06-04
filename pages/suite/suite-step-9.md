---
title:  Run a Backtesting Session
summary: Run a backtesting session using an existing open-source strategy and, once the session is done calculating, analyze the results over the charts.
sidebar: suite_sidebar
permalink: suite-step-9.html
toc: false
---

The testing of strategies and trading ideas is at the core of successful trading, and Superalgos provides a powerful infrastructure for that matter. The instructions below will take you through the operational aspects of running a backtesting session, using an existing open-source strategy, the [Weak Hands Buster](suite-community-weak-hands-buster.html) as an example. The rest of this documentation provides valuable insights on the full potential behind the set of testing tools available.

{% include important.html content="Before running the backtesting session, make sure all Masters indicators in the Binance BTC/USDT market have been calculated until the present time. To do this, refer to the tools you learnt about in previous steps. If all indicators are up to 100%, then you may completely stop the data mining operation and continue with the following instructions." %}

## Start Here

**1. Go to the network hierarchy**.

{% include image.html file='how-to/run-a-backtesting-session-00.gif' url='yes' max-width='100' caption='The image illustrates points 1 to 5 below.' %}

**2. Find the <a data-toggle="tooltip" data-original-title="{{site.data.network.testing_environment}}">testing environment</a> node along with the *Binance* exchange tasks node**.

**3. Find the *Paper & Backtesting Sessions Binance BTC/USDT* task manager**.

**4. Find the *Backtesting WHB* task and click *Run* on the menu**.

**5. Find the *Backtesting WHB* session and click *Run* on the menu**.

Wait a few seconds and notice the progress indication below the backtesting session node. 

{% include note.html content="The session has finished processing when the progress date reaches the present time and eventually disappears. Only then does the simulation become available on the charts. Wait until that happens to follow the next set of instructions." %}

**6. Stop the *Backtesting WHB* task**. Make sure the session finished calculating first.

{% include image.html file='how-to/run-a-backtesting-session-01.gif' url='yes' max-width='100' caption='The indication of progress reaches the present time, stops, and eventually disappears. When that happens, stop the corresponding task.' %}

**7. Open the charting space** and pan the viewport to the left-hand side.

We have set up a chart for each of the trades performed by the strategy from January 2019 and on, so that you may find them quickly.

{% include image.html file='how-to/run-a-backtesting-session-02.gif' url='yes' max-width='100' caption='Notice the charts on the left-hand side of the charting space.' %}

{% include note.html content="If any of the charts is not showing the simulation, you may zoom in and restart the corresponding layers." %}

**8. Take some time to explore each trade by zooming into the charts**.

{% include image.html file='how-to/run-a-backtesting-session-03.gif' url='yes' max-width='100' caption='Every trade is graphically represented over the charts, with all the details including take position rate, initial stop and take profit targets, dynamic targets changing in phases, exit rate, trade results, and plenty more information on the trading simulation panel.' %}


