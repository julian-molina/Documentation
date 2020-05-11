<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Accessing the Charting Space and the Design Space" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

Use the control in the center of the turquoise bar to pull the slider up and down to make more room for either space.

{% include image.html file='how-to/quick-overview-00.gif' url='yes' max-width='100' caption='The dark side of the web application is the design space. Pull the slider up to find the charting space.' %}

You may also use the keyboard as follows:

1. <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>&#8593;</kbd> to close the charting space and open the design space.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>&#8595;</kbd> to close the design space and open the charting space.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>&#8594;</kbd> to incrementally lower the slider.
1. <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>&#8592;</kbd> to incrementally raise the slider.

{% include image.html file='how-to/quick-overview-01.gif' url='yes' max-width='100' caption='The keyboard is your friend.' %}

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