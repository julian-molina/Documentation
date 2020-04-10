<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Find a Hierarchy" %}
{% assign definition = site.data.how_to.find_a_hierarchy %}

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

{% include image.html file='how-to/find-a-hierarchy-00.gif' url='yes' max-width='100' caption='The image illustrates points 1 and 2 below.' %}

**1. Access the design space map.**

Right click anywhere on the design space to access the design space map.

**2. Left-click on your desired destination.**

That should take you to the exact point you clicked on the map.

For your information, the design space is organized over a square perimeter around the workspace node, and each hierarchy is located on one of the cardinal directions. Hierarchies feature an ever-present white ring. The ring hints the direction in which a hierarchy is located.

| Hierarchy | Cardinal Direction | Direction | Keyboard Shortcut (Windows only) |
| :--- | :---: | :---: | :--- |
| **Sparta Data Mine** | North | &#8593; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>S</kbd> (*S for Sparta*) |
| **BRR trading System** | North East | &#8599; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>W</kbd> (*W for Weak Hands Buster*) |
| **WHB Trading System** | East | &#8594; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>B</kbd> (*B for Bull Run Rider*) |
| **Super Scripts** | South East | &#8600; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Z</kbd> (*Z for, well...*) |
| **Network** | South | &#8595; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>N</kbd> (*N for Network*) |
| **Crypto Ecosystem** | South West | &#8601; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>E</kbd> (*E for Ecosystem*) |
| **Charting System** | West | &#8592; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>C</kbd> (*C for Charting System*) |
| **Masters Data Mine** | North West | &#8598; | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>M</kbd> (*M for Masters*) |

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