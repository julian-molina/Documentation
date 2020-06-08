---
title:  Consulting Logs
summary: "Log files are available in a format that should be understandable to most technically-oriented people."
sidebar: suite_sidebar
permalink: suite-troubleshooting-consulting-logs.html
---

Consulting the log files is a crucial step in investigating issues related to the backend application.

Each bot keeps its own set of execution log files, stored under the ```Log-Files``` folder on the root of your Superalgos installation.

Log files contain detailed information about each execution of the bot. As such, a new folder is created for each execution, labeled with the exact DateTime.

Each folder may contain more than one file. Lighter files tend to include data about the initialization stage, while heavier files usually feature the data corresponding to the actual work the bot does.

{% include image.html file='troubleshooting/log-files-01.PNG' url='yes' max-width='100' caption='The latest backtesting session log files folder of the BBTB trading system' %}

{% include note.html content="If reading the log files doesn't help you find the cause of the issue, then make a ```zip``` file with the logs corresponding to the execution where the issue happens so that you may attach it to the issue you will likely need to open on GitHub." %}