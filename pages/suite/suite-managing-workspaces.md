---
title:  Managing Workspaces
summary: "You may have multiple workspaces and manage them using the tab to on the left-hand side of the screen."
sidebar: suite_sidebar
permalink: suite-managing-workspaces.html
toc: false
---

The current workspace is saved as a ```.json``` file in the ```My-Workspaces``` folder every 60 seconds, and is saved also at the moment the browser is closed. You may save it manually using the following hot-key combination: <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd>.

Users may manage multiple workspaces, but only one workspace may be loaded in the system at any point.

To create a new workspace, rename any of the existing ones by changing the label of the workspace node, and save it as explained above.

{% include image.html file='design-space/workspace-01.gif' url='yes' max-width='100' caption='' %}

To load a different workspace, click the tab on the left-hand side of the screen and select one of the available files.

To delete a workspace, delete the corresponding workspace file from within the file system application of your operating system.

{% include tip.html content="Backing up your workspace downloads the same file to your local ```Downloads``` folder. This is too a good way to store old versions in case you ever need to go back to a previous state of affairs." %}

{% include important.html content="Changes made to data mines, trading systems and super scripts shipping with the system may not be saved at the workspace level. If you wish to modify those hierarchies and use them in such modified versions, you need to clone them and modify the clone instead. To do this successfully, you need to learn more about [backups](suite-backups.html) and [clones](suite-clones.html)." %}