---
title:  Debugging a Task
summary: "Run the TaskManager project in your preferred IDE and use the Debug button on the task's menu."
sidebar: suite_sidebar
permalink: suite-developers-debugging-a-task.html
toc: false
---

You may debug any task, either a data mining task or a trading task by following these steps.

## Start Here

**1. Run your Superalgos node** in the usual manner.

**2. Open the TaskServer project in your preferred IDE**, place a breakpoint in the part of the code you wish to debug, and run the TaskServer.

**3. Click the Debug button on the menu** of the task you wish to debug. The request will be routed to the TaskServer running in your IDE.

{% include image.html file='developers/Debugging-tasks.PNG' url='yes' max-width='100' caption='Click the Debug button on the task menu.' %}

**4. Run the trading session** in case it is a trading task.

After a few seconds, execution should pause in the line where you put the breakpoint. Bear in mind the system runs slower in debug mode, thus, it may take a little while for the session to start processing, after loading all dependencies.