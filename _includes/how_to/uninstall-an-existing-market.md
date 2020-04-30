<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Uninstall an Existing Market" %}
{% assign definition = site.data.how_to.uninstall_an_existing_market %}

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

{% include image.html file='how-to/uninstall-existing-markets-01.gif' url='yes' max-width='100' caption='The image shows how to install a new market. Usd the *uninstall market* super action node menu instead.' %}

**1. Expand the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.exchange_markets}}">exchange markets</a> node** of your preferred <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_exchange}}">crypto exchange</a> in the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.crypto_ecosystem}}">crypto ecosystem</a> hierarchy.

{% include /how_to/find-a-hierarchy.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

**2. Click *Run* on the Uninstall Market super action node menu** corresponding to the <a data-toggle="tooltip" data-original-title="{{site.data.crypto_ecosystem.market}}">market</a> you wish to uninstall.

Running the super action deletes all the infrastructure associated with the market, including the following:

1. <a data-toggle="tooltip" data-original-title="{{site.data.network.data_storage}}">Data storage</a> structures of nodes.

2. <a data-toggle="tooltip" data-original-title="{{site.data.network.data_mining}}">Data mining</a> operation for the corresponding exchange and market.

3. <a data-toggle="tooltip" data-original-title="{{site.data.network.testing_environment}}">Testing environment</a> and <a data-toggle="tooltip" data-original-title="{{site.data.network.production_environment}}">production environment</a> <a data-toggle="tooltip" data-original-title="{{site.data.network.task_manager}}">task managers</a> featuring <a data-toggle="tooltip" data-original-title="{{site.data.network.task}}">tasks</a> for all types of trading <a data-toggle="tooltip" data-original-title="{{site.data.network.session}}">sessions</a> referencing the Weak-hands Buster <a data-toggle="tooltip" data-original-title="{{site.data.trading_system.trading_system}}">trading system</a>.

4. A <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.time_machine}}">time machine</a> containing a <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.timeline_chart}}">timeline chart</a> for the market, made readily available on the <a data-toggle="tooltip" data-original-title="{{site.data.charting_space.charting_space}}">charting space</a>.


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