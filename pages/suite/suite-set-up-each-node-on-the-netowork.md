---
title:  Set Up Each Node on the Network
summary: "Install the markets you wish to work with and move tasks to the network nodes you wish to handle those tasks."
sidebar: suite_sidebar
permalink: suite-set-up-each-node-on-the-netowork.html
toc: false
---

Before you continue with the next steps, a quick explanation is in order. What you will do now involves installing markets in network manager node to later move the specific tasks to each node on the network.

When you install a <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market}}">market</a>, several <a data-toggle="tooltip" data-original-title="{{site.data.concepts.structure_of_nodes}}">structures of nodes</a> are created in each of the main sections of the local network node: <a data-toggle="tooltip" data-original-title="{{site.data.network.data_storage}}">data storage</a>, <a data-toggle="tooltip" data-original-title="{{site.data.network.data_mining}}">data mining</a>, <a data-toggle="tooltip" data-original-title="{{site.data.network.testing_environment}}">testing environment</a>, and <a data-toggle="tooltip" data-original-title="{{site.data.network.production_environment}}">production environment</a>. Each set of tasks is grouped by exchange under the corresponding exchange tasks node.

If you are planning to set up a large <a data-toggle="tooltip" data-original-title="{{site.data.network.network_of_nodes}}">network of nodes</a>, it is recommended to install the first set of markets, distribute the corresponding <a data-toggle="tooltip" data-original-title="{{site.data.network.task}}">tasks</a> among the appropriate nodes in the network, and run a few tests before moving forwards. You may repeat this process as many times as required.

## Start Here

**1. Install markets**. In your network manager node, install the first few markets you wish to work with. For example, let's say you wish to run data mining operations for the BTC/USDT, ETH/USDT, and ETH/BTC markets on Binance in your *Machine 01* network node. Then, install those three markets on the network manager node.

{% include /how_to/install-a-new-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**2. Move data mining tasks and data storage session independent data**. Data mining tasks work together with definitions in the data storage section of the network hierarchy, in particular, the so-called <a data-toggle="tooltip" data-original-title="{{site.data.network.session independent data}}">session independent data</a>. Therefore, wherever you decide to run each specific data mining task, the associated session independent data must go with it too.

The easiest way to transfer the data mining and data storage definitions to the remote network node is to do it at the level of the <a data-toggle="tooltip" data-original-title="{{site.data.network.exchange_tasks}}">exchange tasks</a> node in case of data mining tasks, and at the level of the <a data-toggle="tooltip" data-original-title="{{site.data.network.exchange_data_products}}">exchange data products</a> node in the case of data storage session independent data.

Continuing with the example started on the previous step, this is what you would do:

**A.** Detach the Binance exchange tasks node from the data mining section of the network manager node and attach it to the data mining section of the *Machine 01* network node.

**B.** Detach the Binance exchange data products node from the session independent data node of the data storage section of the network manager node and attach it to the session independent data node of the data storage section of the *Machine 01* network node.

{% include image.html file='design-space/trading-farm-01.gif' url='yes' max-width='100' caption='Make sure the exchange data products under session independent data go to the same machine as the exchange tasks under data mining.' %}

That's it! Your data mining operation for those three markets will now run on *Machine 01*.

**3. Test the operation**. You may now test the data mining operation on *Machine 01*. Click *Run* on the Binance exchange tasks node and wait a few seconds. The tasks should start processing. Once the <a data-toggle="tooltip" data-original-title="{{site.data.network.sensor_bot_instance}}">sensor bots instances</a> for each market reach 100%, you may log in to *Machine 01* to verify that the data files are being created as expected.

**4. Move trading sessions and data storage session dependent data**. You will likely want to run trading sessions from a third machine. Trading session tasks work together with definitions in the data storage section of the network hierarchy, in particular, the so-called <a data-toggle="tooltip" data-original-title="{{site.data.network.session_based_data}}">session based data</a>. Therefore, wherever you decide to run each specific trading session task, the associated session based data must go with it too.

The easiest way to transfer trading session tasks and data storage definitions to the remote network node is to do it at the level of the <a data-toggle="tooltip" data-original-title="{{site.data.network.exchange_tasks}}">exchange tasks</a> node in case of trading session tasks, and at the level of the <a data-toggle="tooltip" data-original-title="{{site.data.network.exchange_sessions}}">exchange sessions</a> node in the case of data storage session based data.

Continuing with the example started earlies, this is what you would do:

**A.** Move the Binance exchange tasks node in the production environment of the network manager node to the production environment of *Machine 02*, the third machine. You may set exchange keys and reference the appropriate trading systems at any point, either before or after moving the tasks.

**B.** Move the Binance exchange sessions node from the session based data node of the data storage section of the network manager node to the session based data node of the data storage section of the *Machine 02* network node.

**5. Test the operation**. Once the data mining operation is running up to date, at 100%, you may test your trading sessions on *Machine 2*.

{% include callout.html content="You may repeat steps 1 to 5 for as many markets and machines you wish to work with. You may want to slightly adapt these steps or change the order as you see fit.<br/><br/>Notice that moving the data structures at the level of the exchange tasks node and the exchange data products node is the easiest way to do it. If you wish to move individual tasks in the same exchange to different machines, you may need to manually create the exchange tasks node or exchange data products node in some of the machines. If you do that, remember you need to establish a reference from those nodes to the corresponding crypto exchange node in the Crypto Ecosystem hierarchy.<br/><br/>Also worth noting is that you may also move data structures at the level of the task manager node, and up to the task node itself. A task is the smallest unit you may move to a node in the network. Bear in mind that if you move task managers or tasks, you will need to move the specific single market data nodes and the specific session reference nodes for data mining and trading session tasks repectively.<br/><br/>Finally, uninstalling markets can only be done at the network manager node. If you wish to uninstall markets distributed on different nodes on the network, you may either delete data structures individually, or move data structures back to the network manager node to be uninstalled using the corresponding super action script." type="warning" %}
