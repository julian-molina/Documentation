<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Screen Capture and Sharing" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

* Hit <kbd>Ctrl</kbd> + <kbd>F8</kbd> to capture a static PNG image.

* Hit <kbd>Ctrl</kbd> + <kbd>F9</kbd> to start capturing a GIF video, and hit the same key combination again to end the capture. Once the capture ends, it takes some time to process the capture and generate the final file.

* Hit <kbd>Ctrl</kbd> + <kbd>F10</kbd> to start capturing a WEBM video, and hit the same key combination again to end the capture. WEBM videos are processed instantly.

In all three cases, the browser downloads the resulting file and makes it available in the downloads folder.

{% include note.html content="GIF files tend to grow a lot in long captures, but are more universal, thus more devices can display them properly. WEBM files are a lot more efficient, but do not work in Apple and, potentially, other platforms or devices." %}

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.extended == "more" and include.content != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about {{ title | downcase }}{{plural}}
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