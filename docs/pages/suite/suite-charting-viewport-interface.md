---
title:  Viewport Interface
summary: ""
sidebar: suite_sidebar
permalink: suite-viewport-interface.html
---

## Navigating the Viewport

When you open the charting space's <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.viewport}}">viewport</a>, you may see several charts, depending on the setup of your current <a data-toggle="tooltip" data-original-title="{{site.data.concepts.workspace}}">workspace</a>.

**To move around the viewport**, right-click and drag. You may also use the wheel of the mouse to zoom in and out.

{% include note.html content="Notice how the viewport navigation resembles the navigation in *Google Maps*. You zoom out for the big picture. You zoom in for a closer view of any particular chart to get the details. Keep zooming in and you get the immersive experience... the *street view* of the market." %}

{% include /charting_space/viewport.md heading="more" icon="150-" adding="" configuring="" charts="" content="yes" definition="bold" table="yes" more="yes"%}

## Navigating Time Machines and Embeded Timeline Charts

Each of the charts you see in the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.viewport}}">viewport</a> are actually <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_machine}}">time machines</a>. Time machines are represented by rectangular elements with dark-turquoise boundaries.

Time machines may feature one or more <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.timeline_chart}}">timeline charts</a>, right inside them. In other words, timeline charts live within time machines.

All time machines that are visible at any point are said to be *in focus*.

**To pan the data within a time machine**, left-click within the time machine and drag. You may also use the keyboard as follows:

1. <kbd>Shift</kbd> + <kbd>&#8592;</kbd> to pan to the left.
1. <kbd>Shift</kbd> + <kbd>&#8594;</kbd> to pan to the right.
1. <kbd>Shift</kbd> + <kbd>&#8593;</kbd> to pan upwards.
1. <kbd>Shift</kbd> + <kbd>&#8595;</kbd> to pan downwards.

{% include note.html content="When using the keyboard, all time machines that are in focus are affected by the commands." %}

**To pan the viewport instead of the data of a time machine**, right click and drag. This may be useful when zoomed deep into a time machine and you wish to reach one of it's borders.

{% include /charting_space/time-machine.md heading="more" icon="150-" adding="" configuring="" charts="" content="yes" definition="bold" table="yes" more="yes"%}

{% include /charting_space/timeline-chart.md heading="more" icon="150-" adding="" configuring="" charts="" content="yes" definition="bold" table="yes" more="yes"%}

## Scale Boxes

Zoom in closer or into a time machine and notice the three boxes that move relative to the position of the mouse pointer along the top, right, and bottom borders. These are the *scale boxes*.

**1. At the top** is the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_scale}}">time scale</a> box displaying the current datetime; this is the date and time at the position of the mouse pointer.

**2. To the right** is the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.rate_scale}}">rate scale</a> box displaying the current rate; this is the rate, denominated in the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.quoted_asset}}">quoted asset</a>, at the position of the mouse pointer.

**3. At the bottom** is the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_frame_scale}}">time frame scale</a> box displaying the current time frame, or candle size, if you wish.

Both the time scale and the rate scale may be set to several automatic modes, or to manual mode.

{% include /charting_space/time-scale.md heading="" icon="no" adding="" configuring="" charts="###" content="no" definition="no" table="no" more="no"%}

{% include /charting_space/time-scale.md heading="more" icon="150-" adding="####" configuring="####" charts="" content="yes" definition="bold" table="yes" more="yes"%}

{% include /charting_space/rate-scale.md heading="" icon="no" adding="" configuring="" charts="###" content="no" definition="no" table="no" more="no"%}

{% include /charting_space/rate-scale.md heading="more" icon="150-" adding="####" configuring="####" charts="" content="yes" definition="bold" table="yes" more="yes"%}

{% include /charting_space/time-frame-scale.md heading="" icon="no" adding="" configuring="" charts="###" content="no" definition="no" table="no" more="no"%}

{% include /charting_space/time-frame-scale.md heading="more" icon="150-" adding="####" configuring="####" charts="" content="yes" definition="bold" table="yes" more="yes"%}

## Layer Managers

When you zoom into a <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_machine}}">time machine</a> deep enough, one or more <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.layer_manager}}">layer managers</a> pop up, usually on the top-left corner of the screen. A time machine may have more than one <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.timeline_chart}}">timeline charts</a> embeded and each timeline chart features a layer manager.

**To move a layer manager to the opposite, top-right corner**, left-clicking on the header and dragging it away. Layer managers tend to self-arrange at either of these corners, so you may drop it somewhere next its destination and let it find its place.

{% include note.html content="The order in which layer managers self-arrange is given by the order of precedence of the embeded timeline charts around the time machine node in the designer." %}

**To roll a layer manager up or down**, place the mouse pointer on top of the header and turn the wheel. When the layer manager cannot accommodate all layers in its current lenght, a scrolling bar appears on the right-hand side. To scroll through the layers, place the mouse pointer on top of any of the visible layers and scroll the wheel of the mouse.

**To turn layers *on* and *off***, left-click on the layer. 

* When a layer is *loading*, the layer slot in the layers managers shows the progress with an orange dotted line on top of the layer's name.

* When a layer is *on*, the dotted line turns green.

* When a layer is *off*, there is no line.

* When the layer can't load, the dotted line turns red.

Certain layers may feature a <a data-toggle="tooltip" data-original-title="{{site.data.data_mine.plotter_panel}}">panel</a>. Those which do feature a panel button on the bottom-left corner of the layer slot in the manager.

**To turn panels *on* and *off***, left-click on the panel button. 

Panels t

## Floating Panels

To minimize a panel, click on the small triangle on the right of its title bar. This will automatically position the panel at the bottom of the screen. Clicking again restores the panel to its previous position.

You may also drag and drop the panels by right-clicking on the title bar.

[![Charts-02-Panels](https://user-images.githubusercontent.com/13994516/67281843-a0d1f500-f4d0-11e9-85ad-9843219953b4.gif)](https://user-images.githubusercontent.com/13994516/67281843-a0d1f500-f4d0-11e9-85ad-9843219953b4.gif)