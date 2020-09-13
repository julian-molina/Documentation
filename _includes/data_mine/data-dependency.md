<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Data Dependency" %}
{% assign definition = site.data.data_mine.data_dependency %}
{% assign preposition = "a" %}
{% assign plural = "" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.more == "yes" and include.heading == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.heading != "" and include.heading != "more" %}
{{include.heading}} {{title}}
{% endif %}

{% if include.icon != "no" %} 

{% if include.table == "yes" and include.icon != "no" %}
<table class='definitionTable'><tr><td>
{% endif %}

<img src='images/icons/nodes/png{{include.icon}}/{{ title | downcase | replace: " ", "-" }}.png' />

{% if include.table == "yes" and include.icon != "no" %}
</td><td>
{% endif %}

{% endif %}

{% if include.definition == "bold" %}
<strong>{{ definition }}</strong>
{% else %}
{% if include.definition != "no" %}
{{ definition }}
{% endif %}
{% endif %}

{% if include.table == "yes" and include.icon != "no" %}
</td></tr></table>
{% endif %}

{% if include.more == "yes" and include.content == "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about data dependencies
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

Most bots consume data other bots have produced. Because bots need the data as input for their calculations, processes establish a data dependency with the dataset definitions of other bots. The reference provides the process with all the information needed to decode the dataset, enabling it to perform the required calculations.

[![Indicators-Process-Dependencies-02](https://user-images.githubusercontent.com/13994516/68993034-7840df00-0873-11ea-804d-d24e88ce25f7.gif)](https://user-images.githubusercontent.com/13994516/68993034-7840df00-0873-11ea-804d-d24e88ce25f7.gif)

The image above shows data dependencies in one bot referencing dataset definitions of another bot.

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.content != "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about data dependencies
</summary>
{% endif %}

{% if include.adding != "" %}

{{include.adding}} Adding {{preposition}} {{title}} Node

<!--------------------------------------------- ADDING starts -->

To add a single data dependency, select *Add Data Dependency* on the process dependencies node menu.

{% include tip.html content="Remember that a data dependency must establish a reference to the appropriate dataset definition. When adding data dependencies manually, you also need to manually establish the reference." %}

In cases in which multiple data dependencies are established, you may use the options to create data dependencies in bulk:

* The *Add All Data Mine Dependencies* option on the menu of the process dependencies node adds data mine dependencies for all existing data mines, each of which with the corresponding bot data dependencies mapping every bot in each data mine, and each bot data dependencies node with its data dependencies referencing each dataset definition of each product of each bot.

* The *Add All Data Dependencies* option on the data mine data dependencies node menu performs the same operation as described above, but only for the given data mine. You may use this option after manually adding a single data mine data dependencies node, and manually establishing the reference with the desired data mine. As explained earlier, this action bot data dependencies mapping every bot in the referenced data mine, each bot data dependencies node featuring data dependencies referencing every dataset definition of each product of each bot.

It is unlikely that a bot requires numerous data dependencies, thus, the most common scenario is setting up individual data dependencies and establishing references manually. However, if your bot requires multiple data dependencies, the bulk features may be quite useful, as you may create all data dependencies for any given data mine, and simply delete those that are not required.

<!--------------------------------------------- ADDING ends -->

{% endif %}

{% if include.configuring != "" %}

{{include.configuring}} Configuring the {{title}}

<!--------------------------------------------- CONFIGURING starts -->

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

<!--------------------------------------------- CONFIGURING ends -->

{% endif %}

{% if include.starting != "" %}

{{include.starting}} Starting {{preposition}} {{title}}

<!--------------------------------------------- STARTING starts -->

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

<!--------------------------------------------- STARTING ends -->

{% endif %}

{% if include.more == "yes" %}
</details>
{% endif %}