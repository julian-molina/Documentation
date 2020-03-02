<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "XXXXXXXXXXXXXXXX" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about the {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

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