---
title:  Webhook Notifications
summary: "Receive webhook notifications from other systems and use them as signals in your strategies."
sidebar: suite_sidebar
permalink: suite-webhook-notifications.html
---

## Overview

Superalgos allows you to receive webhook notifications from TradingView or any other system with the capability of sending webhooks. You may use this feature to turn notifications into signals upon which you may act from within your strategies.

The system's Web Server receives notifications and serves them to a sensor bot running as a data mining task. The sensor creates a data product with a number of properties which are made available to be used from within strategies.

The rest of this page describes the set up process and how to use webhook notifications from within Superalgos.

## Set-up the Webhooks Sensor Bot Tasks

The Masters data mine features the definition of the Webhooks sensor bot used to monitor incoming notifications. You need to run an instance of this bot in the data mining section of the exchange and market of your choice. 

The default workspace does not feature these tasks. To create a task for the Webhooks sensor bot, you need to uninstall and re-install the corresponding market.

{% include /how_to/uninstall-an-existing-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

{% include /how_to/install-a-new-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

Once the Webhooks sensor task is set up and running, you are all set at the application level. It's that simple.

## Run a Quick Local Test

Before setting up the actual signal at the corresponding provider, you may run a quick local test that will help you familiarize with the way in which Superalgos handles webhooks.

In the crypto ecosystem node menu, select *Add Signals Providers*. A structure of nodes is added with a signals provider node that allows you to run a little test. Select *Configure Signals Provider* on the menu.

```json
{ 
"webhookURL": "Webhook/New-Message/Trading-View/Binance/BTC-USDT",
"testMessage": "" 
}
```

* ```webhookURL```: This is the URL you need to use for testing purposes. Make sure you refer to the correct exchange and market.

* ```testMessage```: Enter any message, for testing purposes.

Once the test message is configured, select *Send Test Message* on the menu.

## Webhooks Sensor Bot Output

The Webhooks sensor bot outputs a single file, ```Data.json```, in the following location:  ```\Data-Storage\Exchange\Market\Masters\Webhooks\Output\External-Signals\Single-File\```.

You may open the file and see if the content corresponds to what is expected. 

{% include note.html content="Make sure the Webhooks sensor bot task is running. The process is configured to run every 30 seconds by default. If that time has passed, you should find the messages you may have sent." %}

This is what the file may look like, assuming you sent four different test messages:

```json
[[1587998459260,"Trading-View","Sell"],[1587998475409,"Trading-View","Buy"],[1587998530190,"Trading-View","A custom signal I just configured"],[1588000300940,"Trading-View","This is my new message"]]
```

As per the record definition of the Webhooks sensor bot in the Masters data mine, each record in the file features three fields:

* ```timestamp```: the Unix datetime of the message.

* ```source```: the name of the signal provider.

* ```message```: the message set up at the provider's system.

## Using Webhooks Signals from within Strategies

You may use each of the three available properties with the following syntax:

* ```chart.atAnyTimeFrame.externalSignal.timestamp```

* ```chart.atAnyTimeFrame.externalSignal.source```

* ```chart.atAnyTimeFrame.externalSignal.message```

For example, a simple condition evluating to ```true``` when a the last message received is a buy signal from TradingView would look like this:

```js
chart.atAnyTimeFrame.externalSignal.source === "Trading-View" && chart.atAnyTimeFrame.externalSignal.message === "Buy"
```

You may also use the ```previous``` property to check the previous message, as follows:

```js
chart.atAnyTimeFrame.externalSignal.previous.message === "Buy"
```

It may be wise to verify the date of the message, or to check if the message corresponds to a certain time frame. To do that, you may use the ```isItInside``` function as follows:

```js
isItInside(chart.atAnyTimeFrame.externalSignal, chart.at01hs.candle)
```

In the above example, the first parameter ```chart.atAnyTimeFrame.externalSignal``` is the signal object you wish to check, and the second parameter ```chart.at01hs.candle``` is any other object that is delimited in time. In this case, the condition validates ```true``` if the last message falls within the last 1-hour candle.

## Set-up Alerts/Messages at the Provider

You will use the following syntax to craft the URL you need to configure for the webhooks at the provider:

```http://YourIPAddress:Port/Webhook/New-Message/Provider-Name/Exchange/Market```

For example:

```http://182.45.73.1:34247/Webhook/New-Message/Trading-View/Binance/BTC-USDT```

## Set-up Your Network to Accept Incoming Connections

Needless to say, you need to configure your network / router / firewall to allow incoming webhook messages on the corresponding port.

