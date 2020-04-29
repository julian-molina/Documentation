<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Detach and Attach Nodes" %}
{% assign definition = site.data.how_to.detach_and_attach_nodes %}

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

{% include image.html file='design-space/fundamental-design-space-concepts-01.gif' url='yes' max-width='100' caption='Use the *detach* option on the menu to break a relationship.' %}

{{site.data.concepts.chain}}

This feature is useful when testing different configurations, rules or parameters, as it allows to keep alternatives handy in the workspace.

Nodes may be attached only to potential parents. The system limits the way in which nodes may be attached, according to the logic of the information they contain.

{% include note.html content="Nodes may not be detached or attached to frozen nodes. You need to unfreeze them before attaching or detaching." %}

{% include note.html content="The verbs *to chain* and *to attach* may be used interchangeably, as synonyms. Similarly, *to unchain* and *to detach* are both valid." %}

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