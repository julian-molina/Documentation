---
title:  Run a Backtesting Session
summary: Run a backtesting session using an existing open-source strategy and, once the session is done calculating, analyze the results over the charts.
sidebar: suite_sidebar
permalink: suite-step-9.html
toc: false
---

The testing of strategies and ideas is at the core of successful trading, and Superalgos provides a powerful infrastructure for that matter. The instructions below will take you through the operational aspects of running a backtesting session, using an existing open-source strategy, the <a href="https://github.com/Superalgos/Strategy-BTC-WeakHandsBuster" rel="nofollow" rel="noopener" target="_blank">Weak Hands Buster</a> as an example. The rest of this documentation provides valuable insights on the full potential behind the set of testing tools available.

{% include important.html content="Weak Hands Buster uses several Masters indicators. Before running the backtesting session, make sure the indicators have been calculated until the present time&mdash;simply check the charts and see if, for instance, Bollinger Bands are available for the last few days. Bear in mind that backtesting sessions do not require the data mining bots to be running. Feel free to stop your data mining operation as soon as the Masters indicators get to the present time." %}

## Start Here

{% include image.html file='how-to/run-a-backtesting-session-00.gif' url='yes' max-width='100' caption='The image illustrates points 1 to 9 below.' %}

**1. Go to the network hierarchy**.

**2. Find and expand the <a data-toggle="tooltip" data-original-title="{{site.data.network.testing_environment}}">testing environment</a> node**.

**3. Find and expand the *Paper & Backtesting Sessions Binance BTC/USDT*** task manager.

**4. Find and expand the *Backtesting WHB*** task.

**5. Find the *Back WHB* backtesting session** and its <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.parameters}}">parameters</a>.

**6. Go to the <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.time_range}}">time range</a>** parameter and select *Configure Time Range* on the menu.

**7. Change the ```initialDatetime``` year for 2019** instead of 2020, to backtest the strategy all through 2019 and up to the present time. You may edit the configuration right there in the configuration bubble, or copy and paste the following configuration snippet. Once the edit is made, it is saved automatically when you exit the bubble.

```json
{
"initialDatetime": "2019-01-01T00:00:00.000Z",
"finalDatetime": "2020-12-31T23:59:59.999Z"
}
```

**8. Click *Run* on the *Backtesting WHB* task menu**.

**9. Click *Run* on the *Back WHB* session menu**. Wait a few seconds and notice the progress notice below the backtesting session node. When the progress date reaches the present time and eventually disappears, then the session becomes available to visualize on the charts. Wait until that happens to follow the next few instructions.

{% include image.html file='how-to/run-a-backtesting-session-01.gif' url='yes' max-width='100' caption='The image illustrates points 10 to 12 below.' %}

**10. Stop the *Backtesting WHB* task and open the charting space**.

**11. Zoom into the *Binance BTC/USDT* time machine**.

**12. Disable the automatic setting** on the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_scale}}">time scale</a> and <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.rate_scale}}">rate scale</a>.

{% include /charting_space/time-scale.md heading="more" icon="no" adding="" configuring="" charts="###" content="no" definition="no" table="no" more="yes"%}

{% include /charting_space/rate-scale.md heading="more" icon="no" adding="" configuring="" charts="###" content="no" definition="no" table="no" more="yes"%}

{% include image.html file='how-to/run-a-backtesting-session-02.gif' url='yes' max-width='100' caption='The image illustrates points 13 to 17 below.' %}

**13. Find the Backtesting layer manager** somewhere on the top of the screen. If no layer managers show up when you slide the mouse pointer on the upper side of the screen, then go a bit further inside with the level of zoom.

**14. Turn on all the layers**.

**15. Adjust the time scale** to focus on the period of time starting in January 2019.

**16. Change the time frame for the backtesting timeline chart to *01-hs***. Only then will the simulation layers become visible. This is due to the fact the backtesting session was run using that time frame. You did so because the Weak Hands Buster strategy is designed to make decisions upon the closing of the one-hour candle.

**17. Change the time frame of the time machine to *01-hs***. This will give you more detail as to how the strategy behaves and makes decisions.

**18. Explore each trade** and imagine the potential for improving and fine-tuning strategies granted by the ability to analyze every single trade&mdash;and even their events&mdash;directly over the charts.

{% include image.html file='how-to/run-a-backtesting-session-03.gif' url='yes' max-width='100' caption='Every trade is graphically represented over the charts, with all the details including take position rate, initial stop and take profit targets, dynamic targets changing in phases, exit rate, trade results, and plenty more information on the trading simulation panel.' %}