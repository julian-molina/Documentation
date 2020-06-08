<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Check for Errors at the Browser" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about the {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

Open Chrome's DevTools with the <kbd>F12</kbd> key (when the browser is in focus) and click the Console tab. Then go back to Superalgos and reproduce the issue. The console may display *network errors* and *warnings* of different sorts. Those are not important and you may safely ignore them. 

Do pay attention to other kinds of errors, such as files that can not be loaded, or errors in specific system components.
 
{% include image.html file='how-to/report-a-bug-01.png' url='yes' max-width='100' caption='Open Developer Tools and check the console tab for potential errors. Ignore warnings and network errors.' %}

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