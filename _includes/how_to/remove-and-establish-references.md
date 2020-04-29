<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Remove and Establish References" %}
{% assign definition = site.data.how_to.remove_and_establish_references %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.more == "yes" and include.heading == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn how to {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.heading != "" and include.heading != "more" %}
{{include.heading}} How to {{title}}
{% endif %}

{% if include.table == "yes" %}
<table class='definitionTable'><tr><td>
{% endif %}

{% if include.definition == "bold" %}
<strong><i>In brief: </i>{{ definition }}</strong>
{% else %}
{% if include.definition != "no" %}
<strong><i>In brief: </i></strong> {{ definition }}
{% endif %}
{% endif %}

{% if include.table == "yes" %}
</td></tr></table>
{% endif %}

{% if include.more == "yes" and include.content == "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn how to {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

{% include image.html file='design-space/fundamental-design-space-concepts-02.gif' url='yes' max-width='100' caption='Use the *delink* option on the menu to remove a reference.' %}

In case multiple nodes would accept the reference, the one closer to the node where the reference originates will have its ring highlighted. 

Once established, the reference is visually represented by a faint grey dotted line. Such line is visible only when both ends of the reference are visible and when hovering the mouse over the node.

{% include note.html content="Throughout this documentation we may use the verbal phrases *to link*, *to reference* or *to establish a reference* interchangeably, as synonyms." %}

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.extended == "more" and include.content != "more" and include.heading != "more" %}
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