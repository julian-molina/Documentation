---
title:  System Architecture
summary: "A high-level description of the frontend and backend applications behind Superalgos."
sidebar: suite_sidebar
permalink: suite-developers-system-architecture.html
toc: false
---

At the highest level the system is divided into 2 parts:

* **The user interface**: a web app running at the browser.

* **The backend**: a set of Nodejs processes.

## The User Interface

The user interface is a javascript web app called CanvasApp, which has one additional component called Files Component. At the highest conceptual level, the Canvas App runs on a single HTML page, which features an HTML5 canvas object covering the whole page. The UI is rendered at that canvas object within an animation loop, meaning many frames per second are rendered on the same canvas object producing the effect of the UI being alive and responsive to both the mouse and keyboard.

## The backend

At the backend there are 2 different Nodejs processes, running all the time, for the time being, on the same hardware as the UI: 

* The **Web Server**, whose purpose is to serve to the browser the js files of the Canvas App,  its components (for the moment, the Files Component), and the data files needed to plot the charts.

* The **Backend Server**, which contains 3 servers:

  * The **Events Server** enables system-wide events, meaning event-handlers that are accessible from both the backend and the user interface. 

  * The **Task Manager Server** allows the user to launch and stop backend tasks. A task is a Nodejs process hosting a bot.

  * The **Websockets Server** enables real-time communication between the UI and the backend, and also between different processes at the backend.

The backend also includes Nodejs processes that are running only when the user launches a *task*. For each task launched, an instance of the Task Server is put to run by the Task Manager Server. When the task finishes or is stoped by the user, the process exits or is killed by the Task Manager Server.

## The User Interface Architecture

The UI builds a hierarchical structure of objects that maps itself with the elements rendered on the canvas and that the user may interact with. The root of that hierarchy is the canvas object (not to be confused with the HTML canvas object; think of it as an immediate layer on top of it). The next layer on top of the canvas object is composed of objects called *spaces*. 

A space is a conceptual domain in which there is a certain common behavior for the objects inhabiting the space. Users interact with those objects in a certain way.

* The **Top Space** represents the area at the top of the screen where the Superalgos logo is found.

* The **Charting Space** represents the area where all charts live in.

* The **Design Space** represents the area where the user may configure all aspects of the system. The core concept in the design space is that of nodes.

  * **Node**: it is a data structure only. Nodes are related between them in three different ways:

    * **Parent/Child Relationship**: most nodes have a parent, which is usually the one capable of spawning it, and, by this relationship, there are hierarchies of nodes.  

    * **Reference Relationship**: a node may have a Reference Parent, meaning that it holds a reference to another node.

    * **Chain Relationships**: they are used to render the connection between nodes. Usually, a node’s parent is also the node’s chain parent, but not always.

* The **Floating Space** overlaps the design space bringing certain physical properties to the elements living there. It is also where so-called *Floating Objects* and *UIObjects* live. 

  * **UIObjects**: they are the entities you can see on the design space. They are attached to nodes, providing them a user interface.

  * **Floating Objects**: they are objects that once attached to a node provides it with its physical properties (size, attraction and repulsion from each other, for instance). 

* The **Cockpit Space** represents the slider between the charting space and the design space.

* The **Panels Space** represents an overlay area on top of the charting space where all kinds of *panels* live. 

The *Canvas Object* also owns the *Animation object*: it is the object that controls and runs the animation.

Another root object is the *Events Server Client*, which is used to listen and raise system-wide events. It accesses the *Events Server* via the *Websockets Server*. 

The communication between the UI and the *Task Manager Server* to run/stop tasks is via system-wide events (*Websockets Server* plus the *Events Server*).
