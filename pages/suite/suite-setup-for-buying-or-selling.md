---
title:  The Proper Setup for Buying or Selling
summary: "Strategies within a trading system either short or long. Parameters at the level of the trading session define the behavior."
sidebar: suite_sidebar
permalink: suite-setup-for-buying-or-selling.html
toc: false
---

In Superalgos, a <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.trading_system}}">trading system<a/> is designed to accumulate the <a data-toggle="tooltip" data-original-title="{{site.data.network.base_asset}}">base asset</a> as defined in the <a data-toggle="tooltip" data-original-title="{{site.data.network.session}}">trading session</a> <a data-toggle="tooltip" data-original-title="{{site.data.network.parameters}}">parameters</a>. Because the base asset and <a data-toggle="tooltip" data-original-title="{{site.data.network.quoted_asset}}">quoted asset</a> are defined at the level of the trading session, each <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.strategy}}">strategy</a> within a trading system shares the same base asset and the same quoted asset. 

This means that all strategies within a trading system share the same goal: to accumulate the base asset. This also means that an individual strategy and all strategies within a trading system may either *short* or *long* one of the assets in the pair. A strategy can not do both things. It either shorts, or longs.

In Superalgos, you do not directly set up buy or sell orders to take a position. When taking a position, the system places a buy or a sell order depending on how the base asset and quoted asset parameters are set up in relation to how the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market}}">market</a> is listed at the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_exchange}}">exchange</a>:

* When the base asset in the parameters of the trading session matches the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market_base_asset}}">market base asset</a>&mdash;that is, the base asset in the context of the market as listed by the exchange&mdash;Superalgos places a *sell order* to take a position, and a *buy order* to close a position.

* When the base asset in the parameters of the trading session does not match the market base asset&mdash;that is, when the base asset is the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market_quoted_asset}}">market quoted asset</a> instead&mdash;Superalgos places a *buy order* to take a position, and a *sell order* to close a position.

This may be confusing, as the similarity in the names of the concepts of base asset / market base asset, and quoted asset / market quoted asset is prone to some ambiguity.

Think of it in this manner:

* Because the goal is always to accumulate the base asset, when the base asset in the trading session matches the market base asset, the system must place a *sell order* to sell the base asset, and rebuy it later with a *buy order*, hopefully at a cheaper price.

* When the base asset in the trading session is the market quoted asset instead, then the system places a *buy order* to buy the market base asset, and a *sell order* to buy back the market quoted asset.

## Let's Try With an Example

For example, let's assume the market is listed as **BTC/USDT**. In such a case, the market base asset is BTC and the market quoted asset is USDT. 

{% include image.html file='trading-system/BTC-USDT-market.PNG' url='yes' max-width='100' caption='BTC is the market base asset and USDT is the market quoted asset, as defined by the market listing at the exchange.' %}

Let's say your trading system's goal is to accumulate BTC.

* The above means that your base asset (at the level of the trading session) must be BTC and your quoted asset must be USDT.

{% include image.html file='trading-system/trading-session-WHB-parameters.PNG' url='yes' max-width='100' caption='BTC is the base asset and USDT is the quoted asset.' %}

* It also means that the system will place a sell order when taking a position, and will place a buy order to close the trade.

* Under such considerations, the formula of your stop loss in each strategy in the trading system should evaluate to a price *above* the take position rate, and the formula for your take profit target should evaluate to a price *below* the take position rate.

{% include image.html file='trading-system/trading-session-WHB-trade.PNG' url='yes' max-width='100' caption='Stop target above and take profit target below the take position rate.' %}

Now, let's consider another example in the same BTC/USDT market. Let's say you wish to stand on USDT and accumulate USDT, instead of BTC.

* The trading session base asset should be USDT, and the quoted asset should be BTC.

{% include image.html file='trading-system/trading-session-BRR-parameters.PNG' url='yes' max-width='100' caption='USDT is the base asset and BTC is the quoted asset.' %}

* The system will place a buy order to take a position and a sell order to close a position.

* You should set up the stop formula to evaluate to a price below the take position rate and your take profit formula to a price above the take position rate.

{% include image.html file='trading-system/trading-session-BRR-trade.PNG' url='yes' max-width='100' caption='Stop target below the take position rate.' %}
