---
title:  Trading Engine
summary: "The trading engine provides a feedback loop to trading systems so that your strategies may leverage the information processed by the trading bot. The hierarchy provides information in three different contexts: current, last, and exchange orders."
sidebar: suite_sidebar
permalink: suite-trading-engine.html
toc: false
---

{% include /trading_engine/trading-engine.md more="no" heading="" icon="150" definition="bold" table="yes" content="yes" adding="" configuring="" starting="" %}

{% include callout.html type="primary" content="<strong>The trading engine hierarchy is organized by <i>context</i>. That is, the main offspring nodes&mdash;current, last, and exchange orders&mdash;describe the context in which their respective offspring live.</strong>" %}

For example, the concept of an episode&mdash;a whole run of the trading bot&mdash; exists only in the context of the *current* episode, as the system keeps track of one episode at the time only. 

However, the concept of a position is tracked both as the *current position* and the *last position*. This is possible because the system keeps track of all positions occurring within an episode. Superalgos developers thought it was worth it to provide information about positions in both contexts, as this allows you (visually) and your trading system (using simple syntax) to access information about the current position and the last position at any given point in time.

{% include callout.html type="primary" content="<strong>Episodes, positions, and other concepts may also be seen as different contexts too.</strong>" %}

For instance, you may want to know what the ROI is in the context of the episode&mdash;that is, the ROI after several positions have passed&mdash;or the ROI of the current position only.

In other words, some concepts may exist in more than one context. Throughout these pages, you will find definitions and explanations covering each node in the hierarchy. For every concept that may exist in different contexts, you will find the details of how the concept behaves in the different contexts it may exist.

The documentation covers each concept one time only. Each concept is listed within the first context in which the concept appears, according to the structure of the hierarchy. This is to avoid feeding you duplicate content.

{% include tip.html content="The trading engine hierarchy is deep and large, with many ramifications. It is best to learn it through hands-on experimentation, by testing an existing trading system or building your own. It's OK to come back to the documentation often." %}

{% include note.html content="Hover your mouse over a node for a tooltip definition, and click to get all the details." %}

<table class='hierarchyTable'><thead><tr><th><a href='#trading-engine' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.trading_engine}}'><img src='images/icons/nodes/png50/trading-engine.png' /><br />Trading Engine</a></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody>
<tr><td><img src='images/icons/various/png/tree-connector-fork.png' /></td><td><a href='#current' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.current}}'><img src='images/icons/nodes/png50/current.png' /><br />Current</a></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td><img src='images/icons/various/png/tree-connector-fork.png' /></td><td><a href='#last' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.last}}'><img src='images/icons/nodes/png50/last.png' /><br />Last</a></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td><img src='images/icons/various/png/tree-connector-elbow.png' /></td><td><a href='#exchange-orders' data-toggle='tooltip' data-original-title='{{site.data.trading_engine.exchange_orders}}'><img src='images/icons/nodes/png50/exchange-orders.png' /><br />Exchange Orders</a></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>


{% include /trading_engine/current.md more="no" heading="###" icon="150" definition="bold" table="yes" content="yes" adding="" configuring="" starting="" %}

{% include /trading_engine/last.md more="no" heading="###" icon="150" definition="bold" table="yes" content="yes" adding="" configuring="" starting="" %}

### Exchange Orders

We shall cover exchange orders in a separate page, as it is a context of a different nature.
