<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Workspace" %}
{% assign definition = site.data.concepts.workspace %}
{% assign preposition = "the" %}
{% assign plural = "s" %}

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

<img src='images/icons/{{include.icon}}{{ title | downcase | replace: " ", "-" }}.png' />

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
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

The workspace contains:
 
* The <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_ecosystem}}">crypto ecosystem</a>,  the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.charting_space}}">charting space</a>, and the <a data-toggle="tooltip" data-original-title="{{site.data.network.network}}">network</a> <a data-toggle="tooltip" data-original-title="{{site.data.concepts.hierarchy}}">hierarchies</a> with all of their <a data-toggle="tooltip" data-original-title="{{site.data.concepts.node}}">nodes</a>.

* <a data-toggle="tooltip" data-original-title="{{site.data.data_mine.data_mine}}">Data mines</a>, <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.trading_system}}">trading systems</a>, and <a data-toggle="tooltip" data-original-title="{{site.data.super_scripts.super_scripts}}">super scripts</a> created by the user, including clones of those types of hierarchies that may ship with the system. 

* Nodes that may be floating around detached from hierarchies.

* Information regarding the physical position and status of all nodes within the design space, even those detached from the hierarchies.
 
The workspace is not part of any of the hierarchies; instead, it contains them. 

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.extended == "more" and include.content != "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.extended != "no" %}

<!--------------------------------------------- EXTENDED starts -->

The workspace is saved at the browser level automatically every 60 seconds. You may save it manually using the following hot-key combination: <kbd>Ctrl or &#8984;</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd>.

{% include note.html content="Users may manage multiple workspaces, but only one workspace may be loaded in the system at any point." %}

{% include tip.html content="Backing up your workspace is the best way to store this information on disk and have it ready to be restored should you ever need to go back to a previous version. You should back up your workspace once in a while so that you can go back to past versions or recover from the occasional crash too. Also, backups allow you to switch seamlessly from one workspace to another workspace." %}

{% include important.html content="Changes made to data mines, trading systems and super scripts shipping with the system may not be saved at the workspace level. If you wish to modify those hierarchies and use them in such modified versions, you need to clone them and modify the clone instead. To do this successfully, you need to learn more about [backups](suite-backups.html) and [clones](suite-clones.html)." %}

{{include.heading}}## Configuring the Workspace

Select *Configure Workspace* on the menu to access the configuration.

```
{ 
"includeDataMines": ["Masters", "Sparta", "TradingEngines"],
"includeTradingSystems": ["Sparta-WHB-BTC-USDT", "Masters-WHB-ETH-USDT", "Sparta-BRR-BTC-USDT"],
"includeSuperScripts": ["Masters"]
 }
 ```

 * ```includeDataMines``` determines which data mines shall be included in the design space, other than those you may have created. Data mines may be loaded from the ```Data-Mines``` folder in the root of the Superalgos installation.

 * ```includeTradingSystems``` determines which trading systems shall be included in the design space, other than those you may have created. Trading systems may be loaded from the ```Trading-Systems``` folder in the root of the Superalgos installation.

 * ```includeSuperScripts``` determines which super scripts shall be included in the design space, other than those you may have created. Super scripts may be loaded from the ```Super-Scripts``` folder in the root of the Superalgos installation.

<!--------------------------------------------- EXTENDED ends -->

{% endif %}

{% if include.more == "yes" %}
</details>
{% endif %}