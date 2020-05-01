---
title:  Operating a Trading Farm
summary: "Operate tasks in remote nodes pretty much as if they were running on the network manager node."
sidebar: suite_sidebar
permalink: suite-suite-operating-a-trading-farm.html
toc: false
---

The operation of a trading farm is done from within the network manager node. There is no need to use the frontend application on any other node in the network, although you may if you wish.

Running or stopping tasks residing in any of the network nodes is a transparent operation, and works in the same way as if the tasks were in the network manager node. When a task is started, the process takes a snapshot of the state of the network at that point and traces all dependencies before starting the job at hand.

The above means that changes made in the distribution of tasks in the network at any point are recognized by each task upon starting. 

However, entities that don't run in tasks such as time machines and timeline charts in the charting space function with the state of the network upon starting the frontend app. This means that, for example, if you move a data mining task to a different node, the associated chart will show the data in the former node until you refresh the browser.

Finally, uninstalling markets works only for tasks that live at the network manager node. If you wish to uninstall markets distributed on different nodes on the network, you may either delete data structures individually or move data structures back to the network manager node to be uninstalled using the corresponding super action.