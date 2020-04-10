<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Zoom Levels" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about the {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

The viewport handles two particular levels of zoom that may be accessed by double-clicking on a chart. The first double click zooms in and squares the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_machine}}">time machine</a> in the center of the screen, leaving a small margin with the screen borders. At this level of zoom, the scale boxes become visible.

A second double-click zooms in a bit further and the time machine occupies the whole screen. At this level of zoom, layer managers become visible.

{% include note.html content="This double-click feature is available only when the current zoom is at the furthest point, that is, when the viewport is completely zoomed-out." %}

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.extended == "more" and include.content != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn how to {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.extended != "no" %}

<!--------------------------------------------- EXTENDED starts -->

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

<!--------------------------------------------- EXTENDED ends -->

{% endif %}

{% if include.more == "yes" %}
</details>
{% endif %}