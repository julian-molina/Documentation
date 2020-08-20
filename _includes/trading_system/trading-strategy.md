<!-- TITLE AND DEFINITION starts -->

{% assign title = "Strategy" %}
{% assign definition = site.data.trading_system.trading_strategy %}
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
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about strategies
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

The definition of a strategy may be analyzed in three sections:

{% include callout.html type="primary" content="<strong>A strategy is a set of actions occurring in stages</strong>" %}

Strategies are defined in the following steps:

* <a href="suite-strategies-trigger.html" data-toggle="tooltip" data-original-title="{{site.data.trading_system.trigger_stage}}">Trigger Stage</a>
* <a href="suite-strategies-open.html" data-toggle="tooltip" data-original-title="{{site.data.trading_system.open_stage}}">Open Stage</a>
* <a href="suite-strategies-manage.html" data-toggle="tooltip" data-original-title="{{site.data.trading_system.manage_stage}}">Manage Stage</a>
* <a href="suite-strategies-close.html" data-toggle="tooltip" data-original-title="{{site.data.trading_system.close_stage}}">Close Stage</a>

These stages are played in a sequence: once a strategy is *triggered* it looks to *open* a position; once a position is open, it is time to *manage* it as the trade develops; and once a stop or take profit target is hit, it is time to *close* the position.

While stages are played in a sequence, upon execution there may be an overlap. That is, a stage doesn't need to be closed for the next stage to be triggered.

{% include callout.html type="primary" content="<strong>designed to achieve a specific goal within a broader plan</strong>" %}

Your investment plan or trading career may have any number of goals (*e.g.: accumulating a certain asset, diversifying on a basket of coins, annual profit targets, etc.*). If you attempt to achieve two different goals with a single strategy, you may run into problems. It may be doable, but the strategy would certainly be more complex. In any case, the logical thing to do is to analyze each goal separately so that you may design (at least) one clear, straightforward strategy for each goal.

{% include callout.html type="primary" content="<strong>via executing trades</strong>" %}

The definition of strategy points to the concept of *a trade*. A trade is a process that exchanges the base asset for the quoted asset and that—after some time, as the trade develops and targets are hit—exchanges back the quoted asset for the base asset. The first and foremost rule of a trade is to preserve capital and its main goal is to increase it.

That said, Superalgos is flexible enough in the sense that it allows you to override the concept of *a trade*. For example, you may design market-making strategies, or develop all sorts of ideas that don't necessarily fit in that part of the definition.

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.content != "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about strategies
</summary>
{% endif %}

{% if include.adding != "" %}

{{include.adding}} Adding {{preposition}} {{title}} Node

<!--------------------------------------------- ADDING starts -->

To add a strategy, select *Add Strategy* on the trading system node menu. The strategy node is created along with the rest of the basic structure of nodes required to define each of the strategy stages and their events.

{% include tip.html content="You may work with as many strategies as you wish. " %}

{% include important.html content="Strategies within the same trading system work in the same market, have the same base asset, and &mdash;most importantly&mdash;share the same capital. This means that only one strategy in the trading system may be triggered at any one point and that no other strategy in the trading system may be triggered until the first one is triggered off. If you wish to have more than one strategy trading at the same time, then those strategies must be put in separate trading systems. " %}

<!-- ADDING ends -->

{% endif %}

{% if include.configuring != "" %}

{{include.configuring}} Configuring the {{title}}

<!-- CONFIGURING starts -->

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