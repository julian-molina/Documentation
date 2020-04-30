---
title:  Trading Farms
summary: "How to set up a flexible and scalable crypto-trading farm running Superalgos distributed in multiple machines."
sidebar: suite_sidebar
permalink: suite-trading-farms.html
toc: false
---

Superalgos is designed for flexible and scalable trading operations. 

In its current version, the system may be deployed in multiple machines&mdash;as many as desired&mdash;and each machine may constitute a node on the network. Each node on the network may speciallize in a single type of process or handle multiple processes of different types.

For example, you may have a set of machines running data mining operations from multiple exchanges and multiple markets. You may have machines speciallizing in processing indicators and technical studies. And you may have machines speciallizing in running trading sessions.

You may also create network setups with different criteria. For example, you may have machines running combined data mining, data processing and trading operations on a single exchange or market, and other machines running similar combined operations on other exchanges or markets.

In other words, the system allows building any arrangement of machines responding to the organizational logic of your preference.

What is unique about Superalgos is that the system keeps track of the network arrangements you create, and makes sure that all components and data structures in the system can semalessly track dependencies across the network. This means, for example, that trading sessions running on ```Node X``` may access data in ```Node Y``` and ```Node Z``` without requireing any sort of configuration.

On top of that, the operation may be administered entirely from your local machine, or any of the machine in the network.

The explanations below assume that you are familiar with the basic workings of Superalgos, and in particular, of the Network hierarchy. If that is not the case, then please read the [Network pages](suite-network.html) before diving into building a trading farm.

{% include warning.html content="At this stage, Superalgos does not implement any form of security meassures, therefore, the system is to be used in the context of a restricted Local Area Network only." %}

## Set Up the Network

**1. Verify the local area network setup**. Make sure your network is functioning and that machines may access each other's ```Superalgos-master``` folder.
Make a quick list with the name you wish to give to each machine and the corresponding IP address on the network. You will need those to configure each network node. For your information, the default web sockets port used by Superalgos is ```8080```, but you may change it to whatever suits you.

**2. Architect the trading farm**. You need to plan what your operation should look like. For example, which machines in the network should run which data-mining tasks, which machines should run which trading sessions, and so on. As hinted in the introduction, possibilities are endless, so we are not going to cover alternatives here. If you know exactly what you want to do, it should be easy to implement. That said, you are free to explore and experiment as well.

**3. Set up Superalgos on each machine in the network**. Once Superalgos is installed, run the system for the first time and stop the default data-mining operation before it starts processing data. Then close the browser and leave the machine online.

**4. Clean up you local workspace**. You will use one of the machines in the network to set up and manage the Superalgos Network. We call this your *local machine*. For organizational purposes and to avoid confusions later on, it is recommended to clean up your local workspace. That means that you may want to uninstall all the markets that you don't need in your setup.

{% include /how_to/uninstall-an-existing-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**5. Configure the IP Address in your *My Computer* network node**. This is the node corresponding to the local machine. By default, the ```host``` parameter in the node's configuration is set to ```localhost```. To set up a network, you need to change ```localhost``` for the IP address of the machine.

**6. Add and configure a network node for each machine**. 

{% include /network/network-node.md heading="" icon="no" adding="####" configuring="####" starting="" content="no" definition="no" table="no" more="yes"%}

Configure the first node and hit <kbd>F5</kbd> to refresh the page. Once the page reloads, a notice indicating the system is connecting with the new network node will show on the top of the screen. Repeat the process for each machine.

{% include image.html file='design-space/network-farm-01.PNG' url='yes' max-width='100' caption='The message dissapears when the system suceeds in establishing a connection with the new node. ' %}

## Set Up Each Machine

{% include callout.html content="Before you continue with the next steps, a quick explanation is in order. What you will do now involves installing markets in your local machine to later move the specific tasks to each machine on the network. <br/><br/>When you install a market, several structures of nodes are created in each of the main sections of the local network node: data storage, data mining, testing environment and production environment. Each set of tasks is grouped by exchange under the corresponding exchange tasks node.<br/><br/>If you are planning to set up a large network, it is recommended to install the first set of markets, distribute the corresponding tasks among the appropriate nodes in the network, and run a few tests before moving forwards. You may repeat this process as many times as required." type="warning" %}

**7. Install markets**. In your local machine, install the first few markets you wish to work with.

For example, let's say you wish to run data mining operations for the BTC/USDT, ETH/USDT and ETH/BTC markets on Binance in your *Machine 01* network node. Then, install those three markets.

{% include /how_to/install-a-new-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**8. Move data mining tasks and data storage session independent data**. Data mining tasks work together with definitions in the data storage section of the network hierarchy, in particular, the so-called session independent data. Therefore, wherever you decide to run each specific data mining task, the associated session independent data must go with it too.

The easiest way to transfer the data mining and data storage definitions to the remote network node is to do it at the level of the exchange tasks node in case of data mining tasks, and at the level of the exchange data products in the case of data storage session independent data.

Continuing with the example started on step 7, this is what you would do:

**A.** Detach the Binance exchange tasks node from the data mining section of the local network node and attach it to the data mining section of the *Machine 01* network node.

**B.** Detach the Binance exchange data products node from the session independent data node of the data storage section of the local network node and attach it to the session independent data node of the data storage section of the *Machine 01* network node.

{% include image.html file='design-space/trading-farm-01.gif' url='yes' max-width='100' caption='Make sure the exchange data products under session independent data go to the same machine as the exchange tasks under data mining.' %}

That's it! Your data mining operation for those three markets will now run on *Machine 01*.

**9. Test the operation**. You may now test the data mining operation on *Machine 01*. Click *Run* on the Binance exchange tasks node and wait a few seconds. The tasks should start processing. Once the sensor bots reach 100%, you may log in to *Machine 01* to verify that the data files are being created as expected.

**10. Move trading sessions**. You will likely want to run trading sessions from a third machine. All you need to do in that case is move the exchange tasks node in the production environment of the local node to the production environment of *Machine 02*, the third machine. You may set exchange keys and reference the appropriate trading systems at any point, either before or after moving the tasks.

**11. Test the operation**. Once the data mining operation is running up to date, at a 100%, you may test your trading sessions on *Machine 2*.

{% include callout.html content="You may repeat steps 7 to 11 for as many markets and machines you wish to work with. You may want to slightly adapt these steps or change the order as you see fit.<br/><br/>Notice that moving the data structures at the level of the exchange tasks node and the exchange data products node is the easiest way to do it. If you wish to move individual tasks in the same exchange to different machines, you may need to manually create the exchange tasks node or exchange data products node in some of the machines. If you do that, remember you need to establish a reference from those nodes to the corresponding crypto exchange node in the Crypto Ecosystem hierarchy." type="warning" %}
