---
title:  Run a Live Trading Session
summary: Run a live trading session using an existing open-source strategy and follow the progress over the charts.
sidebar: suite_sidebar
permalink: suite-step-10.html
toc: false
---

Running a live trading session is very similar to running a backtesting session. The two main operational differences are:

* Live sessions&mdash;this includes paper trading and forward testing sessions&mdash;require all of the trading system's dependencies to be up to date and running. In this context, *dependencies* are the bots that provide information to the trading system for strategies to make decisions. In the case of <a href="https://github.com/Superalgos/Strategy-BTC-WeakHandsBuster" rel="nofollow" rel="noopener" target="_blank">Weak Hands Buster</a>, this means that all Masters bots must be running and up to date.

* An <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.exchange_account_key}}">exchange account key</a> must be set up to log into your account at the corresponding exchange.

{% include note.html content="We will refer to Binance as the exchange of choice for running this live trading session, assuming you have an account with Binance. This documentation will soon be upgraded to include instructions on how to work with other exchanges. Get your API Key and Secret Key from Binance before you begin." %}

{% include important.html content="This is not financial advice. Although the strategies shipping with Superalgos may be fully functional, we do not make any expressed or implied recommendation as to how you should use them. We share strategies for educational purposes only. Trade at your own risk." %}

{% include live-trading-warning.html %}

## Start Here

### Set Up Your Exchange Account Key

{% include image.html file='how-to/run-a-live-session-00.gif' url='yes' max-width='100' caption='The image illustrates points 1 to 4 below.' %}

**1. Go to the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_ecosystem}}">crypto ecosystem</a> hierarchy**.

{% include /how_to/find-a-hierarchy.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**2. Find and expand the Binance exchange node** under <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_exchanges}}">crypto exchanges</a>

**3. Find the exchange account key node** under <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.exchange_accounts}}">exchange accounts</a> &#8594; <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.user_account}}">user account</a> &#8594; <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.user_keys}}">user keys</a>.

**4. Select *Configure Key* on the menu** and carefully enter your API Key and Key Secret as instructed on the message featured on the configuration bubble. Make sure you don't leave any character foreign to your keys between the double quote marks&mdash;only the exact sequence of characters in the key should go there.

```json
{ 
"codeName": "Paste your exchange API name or label here",
"secret": "Paste your exchange API secret key here. To keep you exchange keys safe, never share data structures you may download from the system, as downloads contain all information in the data structure, including personal information such as exchange keys. Use the share option on the menu instead. The share option strips sensitive information and outputs a file that is safe for sharing."
}
```

### Start Data Mining

{% include image.html file='how-to/run-a-live-session-01.gif' url='yes' max-width='100' caption='The image illustrates points 1 to 3 below.' %}

**1. Go to the network hierarchy**.

**2. Find and expand the data mining node**.

**3. Find the *Masters Binance BTC/USDT* task manager** and select *Run All Tasks* on the menu.

### Run the Live Trading Task and Session

{% include image.html file='how-to/run-a-live-session-02.gif' url='yes' max-width='100' caption='The image illustrates points 1 to 9 below.' %}

**1. Find and expand the <a data-toggle="tooltip" data-original-title="{{site.data.network.production_environment}}">production environment</a> node**.

**2. Find and expand the *Fwd & Live Sessions Binance BTC/USDT*** task manager.

**3. Find and expand the *Live Trading WHB*** task.

**4. Find the *Live Trading WHB* live trading session** and its <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.parameters}}">parameters</a>.

**5. Go to the <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.base_asset}}">base asset</a>** parameter and select *Configure Base Asset* on the menu.

**6. Decide if the default setting for the ```initialBalance``` is correct** and change it if you wish.

```json
{
"initialBalance": 0.001,
"minimumBalance": 0.0001,
"maximumBalance": 0.1
}
```

**7. Click *Run* on the *Live Trading WHB* task menu**.

**8. Click *Run* on the *Live Trading WHB* session menu**.

### Monitor the Live Session on the Charts

Live trading sessions feature the same visualization capabilities as backtesting sessions. Make sure you use the Live Trading layer manager instead of the Backtesting layer manager.