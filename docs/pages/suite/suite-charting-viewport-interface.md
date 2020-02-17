---
title:  Viewport Interface
summary: ""
sidebar: suite_sidebar
permalink: suite-viewport-interface.html
---

## Navigating the Viewport

When you open the charting space's <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.viewport}}">viewport</a>, you may see several charts, depending on the setup of your current <a data-toggle="tooltip" data-original-title="{{site.data.concepts.workspace}}">workspace</a>.

To move around the viewport, right-click and drag. You may also use the wheel of the mouse to zoom in and out.

{% include note.html content="Notice how the viewport navigation resembles the navigation in *Google Maps*. You zoom out for the big picture. You zoom in for a closer view of any particular chart to get the details. Keep zooming in and you get the immersive experience... the *street view* of the market." %}

{% include /charting_space/viewport.md heading="more" icon="150-" adding="" configuring="" charts="" content="yes" definition="bold" table="yes" more="yes"%}


## Timeline Charts and Time Machines

Each of these charts is actually a <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_machine}}">time machine</a>. Time machines are represented by rectangular elements with dark-turquoise boundaries.

Time machines may feature one or mote <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.timeline_chart}}">timeline charts</a>.



## Scale Boxes

Notice the three boxes that move along the borders of the relative to the position of the mouse pointer:

**1.** Above, the current datetime. This is the date and time at the mouse pointer position.

**2.** To the right, the current rate. This is the rate (in this case USDT per BTC) at the mouse pointer position.

**3.** Below, the current time frame (time frame or candle size if you wish). This is the currently displayed time frame—not only for candles but for any other object plotted across available layers.

[![Charts-01-Main-Nodes](https://user-images.githubusercontent.com/13994516/67268983-141a3d80-f4b6-11e9-96cc-c0dc3d9188f7.gif)](https://user-images.githubusercontent.com/13994516/67268983-141a3d80-f4b6-11e9-96cc-c0dc3d9188f7.gif)

## Mouse Navigation

Left-click on the charts and drag to move across the charts.

There are many things you can do with your mouse wheel: 

1. Scroll over the Layers Panel to access layers that may be out of reach downwards.
1. Scroll on top of or next to the datetime to produce a horizontal scaling.
1. Scroll on top of or next to the displayed rate to produce a vertical scaling.
1. Scroll on top of or next to the time frame to change the time frame to available values. 
1. Scroll elsewhere over the chart to zoom in and out. The Platform will not only zoom in and out of the chart, but also automatically adjust the time frame to the most convenient one (for the current zoom level).

[![Overview-05-Mouse-Use](https://user-images.githubusercontent.com/13994516/67268341-7a9e5c00-f4b4-11e9-848d-c520b4a8f1ff.gif)](https://user-images.githubusercontent.com/13994516/67268341-7a9e5c00-f4b4-11e9-848d-c520b4a8f1ff.gif)

## Keyboard Navigation

When on the charts, you may use the following key combinations:

1. <kbd>Shift</kbd> + <kbd>&#8592;</kbd> to pan to the left.
1. <kbd>Shift</kbd> + <kbd>&#8594;</kbd> to pan to the right.
1. <kbd>Shift</kbd> + <kbd>&#8593;</kbd> to pan upwards.
1. <kbd>Shift</kbd> + <kbd>&#8595;</kbd> to pan downwards.

[![Overview-06-Keyboard-Navigation](https://user-images.githubusercontent.com/13994516/67268342-7b36f280-f4b4-11e9-956d-109c65fdd5ba.gif)](https://user-images.githubusercontent.com/13994516/67268342-7b36f280-f4b4-11e9-956d-109c65fdd5ba.gif)

## Layers Panel

This panel includes different layers you may visualize by toggling them on and off with a single mouse click.
The layer title bar can have 3 possible background colors:

**1. Red**: the layer is off.

**2. Green**: the layer is on.

**3. Yellow**: the layer is loading; if it stays yellow, it means it can't load fully.

[![Overview-04-Layers](https://user-images.githubusercontent.com/13994516/67267950-a836d580-f4b3-11e9-931b-81c8dff088ac.gif)](https://user-images.githubusercontent.com/13994516/67267950-a836d580-f4b3-11e9-931b-81c8dff088ac.gif)

## Floating Panels

To minimize a panel, click on the small triangle on the right of its title bar. This will automatically position the panel at the bottom of the screen. Clicking again restores the panel to its previous position.

You may also drag and drop the panels by right-clicking on the title bar.

[![Charts-02-Panels](https://user-images.githubusercontent.com/13994516/67281843-a0d1f500-f4d0-11e9-85ad-9843219953b4.gif)](https://user-images.githubusercontent.com/13994516/67281843-a0d1f500-f4d0-11e9-85ad-9843219953b4.gif)