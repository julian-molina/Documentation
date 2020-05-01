---
title:  Set Up Each Node on the Network
summary: "Install the markets you wish to work with and move tasks to the network nodes you wish to handle those tasks."
sidebar: suite_sidebar
permalink: suite-set-up-each-node-on-the-netowork.html
toc: false
---

Before you continue with the next steps, a quick explanation is in order. What you will do now involves installing markets in your local machine to later move the specific tasks to each machine on the network.

When you install a market, several structures of nodes are created in each of the main sections of the local network node: data storage, data mining, testing environment, and production environment. Each set of tasks is grouped by exchange under the corresponding exchange tasks node.

If you are planning to set up a large network, it is recommended to install the first set of markets, distribute the corresponding tasks among the appropriate nodes in the network, and run a few tests before moving forwards. You may repeat this process as many times as required.
 work with.

## Start Here

**1. Install markets**. In your network manager node, install the first few markets you wish to
For example, let's say you wish to run data mining operations for the BTC/USDT, ETH/USDT, and ETH/BTC markets on Binance in your *Machine 01* network node. Then, install those three markets.

{% include /how_to/install-a-new-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**2. Move data mining tasks and data storage session independent data**. Data mining tasks work together with definitions in the data storage section of the network hierarchy, in particular, the so-called session independent data. Therefore, wherever you decide to run each specific data mining task, the associated session independent data must go with it too.

The easiest way to transfer the data mining and data storage definitions to the remote network node is to do it at the level of the exchange tasks node in case of data mining tasks, and at the level of the exchange data products node in the case of data storage session independent data.

Continuing with the example started on the previous step, this is what you would do:

**A.** Detach the Binance exchange tasks node from the data mining section of the local network node and attach it to the data mining section of the *Machine 01* network node.

**B.** Detach the Binance exchange data products node from the session independent data node of the data storage section of the local network node and attach it to the session independent data node of the data storage section of the *Machine 01* network node.

{% include image.html file='design-space/trading-farm-01.gif' url='yes' max-width='100' caption='Make sure the exchange data products under session independent data go to the same machine as the exchange tasks under data mining.' %}

That's it! Your data mining operation for those three markets will now run on *Machine 01*.

**3. Test the operation**. You may now test the data mining operation on *Machine 01*. Click *Run* on the Binance exchange tasks node and wait a few seconds. The tasks should start processing. Once the sensor bots reach 100%, you may log in to *Machine 01* to verify that the data files are being created as expected.

**4. Move trading sessions**. You will likely want to run trading sessions from a third machine. All you need to do in that case is to move the exchange tasks node in the production environment of the local node to the production environment of *Machine 02*, the third machine. You may set exchange keys and reference the appropriate trading systems at any point, either before or after moving the tasks.

**5. Test the operation**. Once the data mining operation is running up to date, at 100%, you may test your trading sessions on *Machine 2*.

{% include callout.html content="You may repeat steps 1 to 5 for as many markets and machines you wish to work with. You may want to slightly adapt these steps or change the order as you see fit.<br/><br/>Notice that moving the data structures at the level of the exchange tasks node and the exchange data products node is the easiest way to do it. If you wish to move individual tasks in the same exchange to different machines, you may need to manually create the exchange tasks node or exchange data products node in some of the machines. If you do that, remember you need to establish a reference from those nodes to the corresponding crypto exchange node in the Crypto Ecosystem hierarchy.<br/><br/>Also worth noting is that you may also move data structures at the level of the task manager node, and up to the task node itself. A task is the smallest unite you may move to a node in the network." type="warning" %}
