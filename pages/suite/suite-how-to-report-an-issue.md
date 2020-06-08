---
title:  How to Report an Issue
summary: "Reporting an issue is a process that entails doing some basic research, carefully describing how to reproduce the issue, and gathering crucial information."
sidebar: suite_sidebar
permalink: suite-how-to-report-an-issue.html
---

Before you consider reporting an issue, make sure you do everything within your reach to investigate the problem. In most cases, you will find that there is no issue at all and that you were making a mistake, skipping a step in the process, or not fulfilling a requirement.

{% include important.html content="The [troubleshooting guide](suite-how-to-troubleshoot-an-issue.html) takes you through a step-by-step process to investigate your issue and gather all relevant information. Carefully following the guide is a requirement for reporting an issue. If the very act of going through the troubleshooting steps does not solve your issue, then come back here once you have finished gathering the required information, as instructed in the guide. Remember, reporting an issue requires understanding what the issue is about, being able to explain how to reproduce it, and providing all relevant information." %}

## Start Here

### 1. Search for similar issues

Go to the <a href="https://github.com/Superalgos/Superalgos/issues" rel="nofollow" rel="noopener" target="_blank">Issues</a> page in the Superalgos repository and use the search box to find issues that may be similar to yours.

* Search for open and closed issues (remove the ```is:open``` tag).

* Try different keywords you would use to describe the issue.

If you find an issue that is similar to yours, read the whole thread. You may find information conducive to solving the issue, proposed workarounds, or reports on the status of the solution to the issue.

If you believe you have information relevant to the issue that has not yet been offered by other users, then go ahead and reply to the issue with everything you know about your case.

If there are no issues similar to yours, or your issue happens in a different context not addressed in the issues you've found, then go on with the next few steps.

### 2. Are you ready to report an issue?

Please, make an honest assessment of the following questions:

* Have you followed the [troubleshooting guide](suite-how-to-troubleshoot-an-issue.html) to the best of your abilities?

* Have you tested your issue with today's version of the software?

* Have you verified that none of the troubleshooting pages in the documentation addresses and solves your issue?

* Have you captured and saved the associated errors in the browser console or the ```Log-Files``` folder?

* In case your issue is related to the frontend... are you using Chrome to test the issue?

If you answer *no* to any of the above, then you are not ready to open an issue. If you may confidently answer yes to all questions, then please proceed.

### 3. Consider the following

* If the issue may be reproduced on one of the official workspaces, then report the issue as such. Issues occurring on custom workspaces have a lower priority.

* Issues that may not be reproduced have lower priority than those that may be reproduced.

### 4. Open a new issue

Click the *New Issue* button and select *Get Started* on the *Bug report* item. The following form will open:

{% include image.html file='troubleshooting/report-an-issue-01.PNG' url='yes' max-width='100' caption='Carefully complete the form following the below guidelines' %}

##### Title

Do your best to describe the issue in a single, short sentence. Take your time. A good practice is describing what happens and in which context. For example: "WHB backtest stops short of finalDatetime".

##### Context

Complete and adjust the contents leaving the information that fits your case and deleting the information that doesn't.

**Operating System:** Windows / MacOs / Linux / Other (include the version on either case)

**Software version:** today's master branch / today's develop branch 

**Workspace version:** default Workspace.json (Getting Started Guide) / Simple Workspace.json / Workspace - Binance - WHB - BBTB.json / My custom workspace 

**Reproducible:** the issue may / may not be reproduced.

##### Explain your issue

1. Clearly explain what you wish to accomplish.

1. Explain, step by step, what you've done to achieve the goal. The Team will follow these steps to reproduce the issue, so be precise.

1. Explain what is the result you expect from your actions.

1. Explain what happens instead of the expected results.

1. Explain what errors you have found on-screen, on the browser console application, or in the ```Log-Files``` folder.

##### Reproduce the issue on video

The most important aspect of investigating an issue is being able to reproduce it. Capturing a video showing the steps that lead to the issue would be of great help.

If the issue happens within the browser, you may use the systems' video capture feature:

{% include /reuse/screen-capture-and-sharing.md content="yes" extended="no" %}

In case the issue does not happen at the browser, for example, if it happens at the console, <a href="https://www.cockos.com/licecap/" rel="nofollow" rel="noopener" target="_blank">LICEcap</a> is a lightweight, simple system that can help you capture GIF videos outside of Superalgos.

{% include note.html content="Bear in mind that GitHub issues accept files 10MB and lighter only." %}

##### Attach relevant log files

If you have on-screen errors or errors at the browser console, screen captures are fine.

If you have errors in the backend, attach the logs you have collected while following the [troubleshooting guide](suite-how-to-troubleshoot-an-issue.html#9-may-this-be-an-issue-with-the-backend-application).

{% include note.html content="GitHub issues do not allow uploading JSON files. Make a ZIP file with all relevant logs instead." %}

##### Custom workspace?

If the issue happens under specific conditions on a custom workspace, attach a [share](suite-shares.html) of the workspace. **Do not attach backups as those may contain personal information such as API Keys**. 

{% include important.html content="Upload your workspace to the issue only if you feel comfortable with sharing it openly. If there are data structures that you prefer not to share, consider removing them so that you may share the non-sensitive bits only. If the issue happens precisely with the sensitive data structures in your workspace, then clearly explain the matter and wait for further instructions." %}
 
### 5. Enable Github notifications

Make sure you enable GitHub notifications when someone responds to the issue, as developers may want to ask for more information.