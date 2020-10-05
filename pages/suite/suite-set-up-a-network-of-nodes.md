---
title:  Set Up a Network of Nodes
summary: "Install Superalgos on each machine, set up a network manager node, create and set up a network node for each machine."
sidebar: suite_sidebar
permalink: suite-set-up-a-network-of-nodes.html
toc: false
---

This page does not go through the process of setting up a computer network. Instead, it assumes the network is already set up. So, do verify the local area network setup and make sure your computer network is functioning properly before starting. 

Make a quick list with the name you wish to give to each <a data-toggle="tooltip" data-original-title="{{site.data.network.network_node}}">node</a> and the corresponding IP address on the network. You will need those to configure each network node. 

{% include note.html content="For your information, the default web sockets port used by Superalgos is ```8081```." %}

Also, you may want to plan what your operation should look like. For example, which nodes in the network should run which data-mining tasks, which nodes should run which trading sessions, and so on. As hinted in the [fundamental concepts](suite-fundamental-trading-farms-concepts.html) page, possibilities are endless, so we are not going to cover alternatives here. If you know exactly what you want to do, it should be easy to implement. That said, you are free to explore and experiment as well.

## Start Here

**1. Set up Superalgos on each machine**. Once Superalgos is installed, run the system for the first time using the ```node run noBrowser``` command. The ```noBrowser``` parameter runs the backend without fireing up the frontend. 

{% include tip.html content="For minicomputers or single-board computers such as the Raspberry Pi, use ```node run noBrowser minMemo```
 to run the app. ```minMemo``` sets up the system to run with minimal RAM memory requirements." %}

Leave the machine online, with the backend running.

**2. Prepare a machine *network manager node***. 

You may want to use one of the nodes in the network to set up and manage the <a data-toggle="tooltip" data-original-title="{{site.data.network.network_of_nodes}}">network of nodes</a>. We call this your *network manager node*. This is the only machine on the network that needs to run the frontend.

For organizational purposes and to avoid confusion later on, it is recommended to clean up the local workspace of this node. That means that you may want to uninstall all the markets that you don't need.

{% include /how_to/uninstall-an-existing-market.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

You also need to configure the IP Address in the network manager node. By default, the ```host``` parameter in the node's configuration is set to ```localhost```. To be a part of a network of nodes, you need to change ```localhost``` to the IP address of the machine.

**3. Add and configure a network node for each machine**.

{% include /network/network-node.md heading="" icon="no" adding="####" configuring="####" starting="" content="no" definition="no" table="no" more="yes"%}

Configure the first node and hit <kbd>F5</kbd> to refresh the page. Once the page reloads, a notice indicating the system is connecting with the new network node will show on the top of the screen. Repeat the process for each machine.

{% include image.html file='design-space/network-farm-01.PNG' url='yes' max-width='100' caption='The message dissapears when the system suceeds in establishing a connection with the new node. ' %}