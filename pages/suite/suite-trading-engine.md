---
title:  Trading Engine
summary: "The trading engine provides a feedback loop to trading systems so that your strategies may leverage the information processed by the trading bot. The hierarchy provides information in three different contexts: current, last, and exchange orders."
sidebar: suite_sidebar
permalink: suite-trading-engine.html
toc: false
---

{% include /trading_engine/trading-engine.md more="no" heading="" icon="150" definition="bold" table="yes" content="yes" adding="" configuring="" starting="" %}

### Context

The trading engine hierarchy is organized by *context*. That is, the main offspring nodes&mdash;current, last, and exchange orders&mdash;describe the context in which their respective offspring live.

For example, the concept of an episode&mdash;a whole run of the trading bot&mdash; exists only in the context of the *current* episode, as the system keeps track of one episode at the time only. 

However, the concept of a position is tracked both as the *current position* and the *last position*. This is possible because the system keeps track of all positions occurring within an episode. Superalgos developers thought it was worth it to provide information about positions in both contexts, as this allows you (visually) and your trading system (using simple syntax) to access information about the current position and the last position at any given point in time.

{% include callout.html type="primary" content="<strong>Episodes, positions, and other concepts may be seen as different contexts too.</strong>" %}

For instance, you may want to know what the ROI is in the context of the episode&mdash;that is, the ROI after several positions have passed&mdash;or the ROI of the current position only.

In other words, some concepts may exist in more than one context. Throughout these pages, you will find definitions and explanations covering each node in the hierarchy. For every concept that may exist in different contexts, you will find the details of how the concept behaves in the different contexts it may exist.

The documentation covers each concept one time only. Each concept is listed within the first context in which the concept appears, according to the structure of the hierarchy. This is to avoid feeding you duplicate content.

### Monitoring Runtime Data on the Design Space

Each of the nodes in the hierarchy may display its value on the design space, right below the icon representing the node. This is how you may monitor every piece of information processed by the trading bot, at any given point in time. 

{% include callout.html type="primary" content="<strong>With this visualization feature, you gain insight into what happens at every moment.</strong>" %}

To see the value of each node rendered on-screen, you must:

**1. Run a trading session**. Start with a backtest, so that you may get a quick feel of how the trading engine hierarchy displays data spanning any period.

**2. Go to the chart displaying the simulation** and find one of the positions. 

**3. Turn on the *Current Position* layer** in the *Trading Engine* layer manager. This layer monitors the position structure of nodes under the current node, that is, the information regarding current positions.

**4. Split the screen** to make room for both the design space and the charting space.

**5. Position the view on the design space** so that you may see the corresponding structure of nodes.

**6. Slide the pointer of the mouse over the charts**, across the position, and notice how the values for each node displayed on the design space change. Each node displays the corresponding value for each candle.

{% include tip.html content="Much of the data handled by the trading engine may also be visualized over the charts through the layers and panels in the *Trading Charts* layer manager. Please refer to the explanations on the trading system section of the documentation." %}

{% include tip.html content="The trading engine hierarchy is deep and large, with many ramifications. It is best to learn it through hands-on experimentation, by testing an existing trading system." %}

{% include note.html content="Hover your mouse over a node for a tooltip definition, and click to get all the details." %}

<table class='hierarchyTable'><thead><tr><th><a href='#trading-engine' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.trading_engine}}'><img src='images/icons/nodes/png50/trading-engine.png' /><br />Trading Engine</a></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody>
<tr><td><img src='images/icons/various/png/tree-connector-fork.png' /></td><td><a href='#current' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.current}}'><img src='images/icons/nodes/png50/current.png' /><br />Current</a></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td><img src='images/icons/various/png/tree-connector-fork.png' /></td><td><a href='#last' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.last}}'><img src='images/icons/nodes/png50/last.png' /><br />Last</a></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td><img src='images/icons/various/png/tree-connector-elbow.png' /></td><td><a href='#exchange-orders' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.exchange_orders}}'><img src='images/icons/nodes/png50/exchange-orders.png' /><br />Exchange Orders</a></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>


{% include /trading_engine/current.md more="no" heading="###" icon="150" definition="bold" table="yes" content="yes" adding="" configuring="" starting="" %}

{% include /trading_engine/last.md more="no" heading="###" icon="150" definition="bold" table="yes" content="yes" adding="" configuring="" starting="" %}

### Exchange Orders

We shall cover exchange orders in a separate page, as it is a context of a different nature.
