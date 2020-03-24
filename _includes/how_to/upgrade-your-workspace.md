<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Upgrade Your Workspace" %}
{% assign definition = site.data.how_to.upgrade_your_workspace %}

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

Sometimes a new workspace may become available. If you wish to upgrade to the latest workspace, follow these instructions:

**1. Locate the file ```Workspace.json```** in the root of the ```Superalgos-master``` folder.

**2. Left-click on the file and drag it over the browser** where the system is running. You will notice the system recognizes your intent and pulls the slider up, showing the <a data-toggle="tooltip" data-original-title="{{site.data.concepts.design_space}}">design space</a>.

**3. Drop the workspace file on the design space** and wait for a few seconds. You should see a ring around the workspace icon, indicating the progress of the import action. Once the ring disappears, the import operation is over and you are free to start using the system.

{% include image.html file='how-to/import-the-workspace-00.gif' url='yes' max-width='100' caption='Drag and drop the workspace on the design space, and wait for a few seconds until the progress ring disappears.' %}

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