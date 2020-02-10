---
title:  "Interface"
summary: "Navigation allows the use of mouse and keyboard. You may also create shortcuts. Node's menu allows controlling the physics of the environment and provides backup, share and clone functions."
sidebar: suite_sidebar
permalink: suite-designer-interface.html
---

## Navigation

Left-click on the black background and drag to move around the workspace.

You may also use the following key combinations on your keyboard:

1. <kbd>Ctrl or &#8984;</kbd> + <kbd>&#8592;</kbd> to pan to the left.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>&#8594;</kbd> to pan to the right.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>&#8593;</kbd> to pan upwards.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>&#8595;</kbd> to pan downwards.

You may also use your keyboard as follows:

1. <kbd>Alt</kbd> + <kbd>&#8593;</kbd> to close the charts and open the designer.
1. <kbd>Alt</kbd> + <kbd>&#8595;</kbd> to close the designer and open the charts.
1. <kbd>Alt</kbd> + <kbd>&#8594;</kbd> to open both the designer and the charts, assigning each one-half of the screen.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>&#8593;</kbd> to pull the separation bar up incrementally.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>&#8595;</kbd> to pull the separation bar down incrementally.

## Node Shortcuts

You may define shortcuts for frequently-used nodes with the following procedure:

1. Hover the mouse pointer over the target node until the menu opens up. This puts the node *in focus*.
1. Click <kbd>Ctrl or &#8984;</kbd> + <kbd>Alt</kbd> + your preferred key to assign the shortcut.
1. A sign will appear below the node confirming the assignation of the shortcut.

[![Shortcuts](https://user-images.githubusercontent.com/13994516/70344838-f123cd00-185a-11ea-819f-92c4cf1e93ea.gif)](https://user-images.githubusercontent.com/13994516/70344838-f123cd00-185a-11ea-819f-92c4cf1e93ea.gif)

Repeat the same procedure to remove a shortcut.

{% include note.html content="When attempting to assign a shortcut with a keyboard combination that is already in use, the platform will notify of the issue. If you insist by hitting the same keyboard combination two more times, the platform will assign the shortcut as expected." %}

## Node's Menu

Hovering the mouse pointer over nodes causes a menu to pop up. In this situation, the node is *in focus*.

### Arrangement Features

The designer functions under the paradigm of a *self-organizing workspace* in which nodes tend to find their place guided by certain laws of physics, and constrained by their chain relationships.

This self-organizing paradigm saves users the effort of maintaining the arrangement of nodes in a logical manner, in particular when manipulating or creating new nodes.

However, there will be times in which you will want to override this self-organizing nature. The following menu options are tools that will help you manipulate the arrangement of nodes, overriding the physics that affect their floating nature.

| Icon | Pinned / Unpinned |
| --- | --- |
| ![fix-pinned](https://user-images.githubusercontent.com/13994516/63041034-2df04080-bec7-11e9-88d3-8b7c1d42a666.png) | The node is pinned to the workspace on a specific ```[x, y]``` coordinate. This status overrides any other setting affecting the node's mobility. Only direct user action by clicking and dragging may move a pinned node. |
| ![menu-fix-unpinned](https://user-images.githubusercontent.com/13994516/63041045-35afe500-bec7-11e9-8f21-c8b3b66d3a0b.png) | When a node is unpinned, it is free to be affected by other settings, or find its place floating on the workspace. |


| Icon | Freeze / Unfreeze |
| --- | --- |
| ![menu-mobility-freeze](https://user-images.githubusercontent.com/13994516/63041051-39436c00-bec7-11e9-8194-7cdd113147e4.png) | Clicking the *freeze* option freezes the node's chain connections with its parent and offspring. Connecting lines turn blue. If you freeze the head node of a hierarchy, then the whole hierarchy is frozen. Freezing node structures is effective only when nodes are loose, that is, when they are not affected by angle or distance settings and are unpinned. In such cases, freezing releases CPU resources, as the platform stops calculating node's positions and status. | 
| ![menu-mobility-unfreeze](https://user-images.githubusercontent.com/13994516/63041053-3b0d2f80-bec7-11e9-8b6f-ebe50dcb4d25.png) |  Clicking the *unfreeze* option unfreezes connections. If you click the option to unfreeze a node and the node does not change its status, it may be because a higher node in the hierarchy is still frozen. | 

| Icon | Collapse / Expand |
| --- | --- |
| ![menu-tree-minus](https://user-images.githubusercontent.com/13994516/63041070-44969780-bec7-11e9-9a42-3f13264b3ed2.png) | Clicking the _minus_ button collapses the structure, hiding offspring nodes. This also has the effect of releasing CPU resources as the platform stops calculating their position and status. In general, it is good practice to keep hierarchies closed when not being actively worked on. | 
| ![menu-tree-plus](https://user-images.githubusercontent.com/13994516/63041077-45c7c480-bec7-11e9-965c-38e4fd706c38.png) | Clicking the _plus_ button expands the structure of offspring nodes. | 

| Icon | Angle to Parent &mdash; Click to cycle through the different options. |
| --- | --- |
| ![360](/images/icons/angle-to-parent-360.png) | The node is locked to a *rotational symmetry* around its parent node, with sibling nodes using the same setting. The symmetry spans **360 degrees**, and the connection line with the parent node is orange.| 
| ![180](/images/icons/angle-to-parent-180.png) | The slot of the symmetry around its parent node is limited to **180 degrees**, and the connection line remains orange.| 
| ![90](/images/icons/angle-to-parent-090.png) | The slot of the symmetry around its parent node is limited to **90 degrees**, and the connection line remains orange.| 
| ![45](/images/icons/angle-to-parent-045.png) | The slot of the symmetry around its parent node is limited to **45 degrees**, and the connection line remains orange.| 
| ![00](/images/icons/angle-to-parent-000.png) | The *rotational symmetry* is disabled and the node may take any position. The connection line with its parent turns yellow.| 

| Icon | Distance to Parent &mdash; Click to cycle through the different options. |
| --- | --- |
| ![025](/images/icons/distance-to-parent-025.png) | The node is locked to a distance from its parent node that is **0.25X** of the distance from the parent to its parent. | 
| ![050](/images/icons/distance-to-parent-050.png) | The node is locked to **0.5X** of the distance. | 
| ![100](/images/icons/distance-to-parent-100.png) | The node is locked to **1X** of the distance. | 
| ![150](/images/icons/distance-to-parent-150.png) | The node is locked to **1.5X** of the distance. | 
| ![200](/images/icons/distance-to-parent-200.png) | The node is locked to **2X** of the distance. | 
| ![000](/images/icons/distance-to-parent-000.png) | The distance setting is dissabled and the node may assume any distance to its parent. | 

### Productivity Features

The rest of the menu options available in most nodes are the following:

| Icon | Action |
| --- | --- |
| ![menu-backup](https://user-images.githubusercontent.com/13994516/63045559-e66eb200-bed0-11e9-8f4d-6385147161fb.png) | **Backup**: Downloads a JSON file with the data structure and references concerning the particular node and the structure of offspring nodes in the hierarchy. Use this feature to save your entire workspace or any particular structure of nodes within your workspace so that you may later restore the information, including all references, should you need to. For your reference, the file downloaded is named ```Backup``` followed by the name of the node you are backing up. |
| ![clone](https://user-images.githubusercontent.com/13994516/71024964-5d79b880-2106-11ea-9f9a-753b96d98861.png) | **Clone**: Downloads a JSON file containing information similar to a backup. The main difference is that the feature is built to facilitate the production of identical copies of any particular structure of nodes of a hierarchy, or a complete hierarchy. Use this feature to accelerate your work process when you need to replicate nodes, for example, to create multiple testing sessions. The file downloaded is named ```Clone``` followed by the name of the node you are cloning. |
| ![menu-share](https://user-images.githubusercontent.com/13994516/63045561-e7074880-bed0-11e9-88a2-cf99a0ede94e.png) | **Share**: Downloads a JSON file containing information similar to a backup. The only difference is that no personal information is included. This is particularly important so that you do not share sensitive information accidentally, such as your API keys. Always use this function when you intend to share work. Do not share your backups. The file downloaded is named ```Share``` followed by the name of the node you are sharing. |
| ![menu-delete](https://user-images.githubusercontent.com/13994516/63045560-e66eb200-bed0-11e9-8b67-feb72b4ab253.png) | **Delete**: Deletes the node and all its offspring. Confirmation in the form of an additional click is required. |