---
title:  How to Report a Bug
summary: "It is of the utmost importance for developers to understand how to reproduce the issue."
sidebar: suite_sidebar
permalink: suite-how-to-report-a-bug.html
---

We highly appreciate bug reports. This is what you need to do when you run into an issue you wish to report:

**1. Make sure you are running the latest patches**. The <a href="ttps://github.com/Superalgos/Superalgos/" rel="nofollow" rel="noopener" target="_blank">Superalgos respository</a> shows when the latest patch was commited to the master branch. If you installed the software before that date, you should [upgrade your installation](suite-upgrading-your-existing-instalation.html) and see if you can reproduce the issue with the latest version. If you can't, the issue may have been already resolved.

{% include image.html file='how-to/report-a-bug-00.gif' url='yes' max-width='100' caption='Flick the mouse wheel while pressing the Ctrl or Command key.' %}

**2. Go to the <a href="ttps://github.com/Superalgos/Superalgos/issues" rel="nofollow" rel="noopener" target="_blank">Issues</a> page** in the Superalgos repository.

**3. Search for similar existing issues**. If you find one similar to yours, you may find helpful to follow the thread, and may contribute by introducing new information about the issue.

**4. Open a new issue only if there are no existing similar issues**. Do your best to describe the problem as thoroughly as possible.

{% include tip.html content="Developers will be interested in knowing how to reproduce the issue in their systems, so please describe the process that leads to the issue as clearly as possible. Capturing a GIF video showing the steps that lead to the issue would be of great help!" %}

If the issue happens within the browser, you may use the systems' video capture feature:

{% include /reuse/screen-capture-and-sharing.md content="yes" extended="no" %}

In case the issue does not happen at the browser, for example, if it happens at the console, <a href="https://www.cockos.com/licecap/" rel="nofollow" rel="noopener" target="_blank">LICEcap</a> is a lightweight, simple system that can help you capture GIF videos outside of Superalgos.

{% include note.html content="Bear in mind that GitHub issues accept files 10MB and lighter only." %}

If the issue seems to happen under specific conditions, you may want to share a backup of the corresponding data structures with developers. To do this, go to the concerned node and select _Share_ in the menu. A file containing the structure of nodes with no personal information downloads to your browser's download folder. Upload this file to the issue only if you feel comfortable with sharing it openly. If not, then wait for developers to contact you.
 
If the issue happens while using the system at the browser, then please include a screen capture of Chrome's Console. Open DevTools with the <kbd>F12</kbd> key (when the browser is in focus) and click the Console tab, then go back and reproduce the issue. Take a screen capture of the Console and paste it along with your report.
 
{% include image.html file='how-to/report-a-bug-01.gif' url='yes' max-width='100' caption='Open Developer Tools and check the console tab for potential errors.' %}

Feel free to also include screen captures of the frontend if there is anything relevant you wish to show developers.

**5. Enable Github notifications when someone responds to the issue**, as developers may want to ask questions.