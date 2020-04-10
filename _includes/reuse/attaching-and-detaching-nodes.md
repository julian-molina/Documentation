<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Attaching and Detaching Nodes" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

{{include.heading}}## Attaching and Detaching Nodes

{{site.data.concepts.chain}}

This feature is useful when testing different configurations, rules or parameters, as it allows to keep alternatives handy in the workspace.

To detach a node, right-click on it and drag it away from the parent node. To attach a node, right-click on it and move it closer to the node you wish to attach it to. 

{% include image.html file='design-space/fundamental-design-space-concepts-01.gif' url='yes' max-width='100' caption='You may also use the *detach* option on the menu to break a relationship.' %}

Nodes may be attached only to potential parents. The system limits the way in which nodes may be attached, according to the logic of the information they contain.

{% include note.html content="Nodes may not be detached or attached to frozen nodes. You need to unfreeze them before attaching or detaching." %}

{% include note.html content="The verbs *to chain* and *to attach* may be used interchangeably, as synonyms. Similarly, *to unchain* and *to detach* are both valid." %}

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