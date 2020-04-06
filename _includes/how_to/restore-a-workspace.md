<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Restore a Workspace" %}
{% assign definition = site.data.how_to.restore_a_workspace %}

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

{% include image.html file='how-to/import-the-workspace-00.gif' url='yes' max-width='100' caption='Drag and drop the workspace on the design space, and wait for a few seconds until the progress ring disappears.' %}

Sometimes a new workspace may become available, or you may want to go back to the original state of the workspace as it ships with the system. Or maybe you wish to go back to an earlier version of the workspace you may have backed up.

In any case, to restore a workspace file, follow these instructions:

**1. Locate the workspace file you wish to restore**. The workspace that ships with the system is ```Workspace.json``` in the root of the ```Superalgos-master``` folder. Workspaces you may have backed up are stored in the Chrome's ```Downloads``` folder.

**2. Go to the design space and locate the Workspace icon**.

**3. Left-click on the Workspace file, drag it and drop it over the browser, right on top of the Workspace icon**. Wait for a few seconds. You should see a ring around the workspace icon, indicating the progress of the import action. Once the ring disappears, the import operation is over and you are free to start using the system.

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