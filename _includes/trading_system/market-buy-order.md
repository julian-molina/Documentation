<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Market Buy Order" %}
{% assign definition = site.data.trading_system.market_buy_order %}
{% assign preposition = "a" %}
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
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

Traders usually use market orders when the priority is the certainty of execution over the rate of execution. Depending on the size of the order and the liquidity of the particular market/exchange, market orders may experience more or less slippage.

###### Market Orders' Rate

Users have no control over the rate at which a market order is filled. The exchange fills the order with available bids/asks at the time of execution.

{% include tip.html content="The information below this banner is valid for all types of orders." %}

###### Order Size

The size of an order is set as a percentage of the size that the particular algorithm is allowed to execute. Because each execution algorithm may define multiple orders, the typical scenario is that all orders defined within an algorithm add up to 100% of the size allocated to the algorithm. 

However, it is up to the user how to manage this setting, as different hacks may be found to achieve different behaviors.

If orders defined add up to more than 100% of the size allocated to the algorithm, the trading engine places the last order with a size matching the established limit, thus modifying the defined size to match the limit.

Similarly, the trading engine checks the overall position size limit established by the target size defined under the initial targets node. If the order size as defined would cause the target size to be breached, then the order size is lowered to match the limit.

Pretty much like the user may decide to define the size of orders within an algorithm above and below the 100% mark, the same is true when defining multiple algorithms. In other words, the user may choose to set up algorithms whose combined sizes amount to more or less of target size defined under the initial targets node, that is, more or less than 100%.

In cases in which the combined sizes amount to less than 100%, the target size would be partially filled at best. On the other hand, in cases in which the combined sizes amount to more than 100%, then the orders and/or algorithms would compete with each other.

{% include note.html content="See the order's configuration to learn how to set up the order size." %}

###### Filling of Orders

The trading engine keeps track of the amounts filled based on the feedback obtained from the exchange and makes the information available in the size filled node. The node is present in multiple contexts, such as the particular stage (open and close) or the particular order type, and is denominated both in the base asset and quoted asset. You may learn more about how to track the size filled on the trading engine pages.

###### Closing of Orders

Orders may be closed upon the occurrence of the following two events:

* The exchange reports the order was filled. In such a case, the trading engine closes the order.

* The cancel order event is triggered. This is an event the user may configure with the typical set up of situations and conditions.

###### Spawning Multiple Orders

All of the available types of orders may be configured so that multiple orders may be spawned, one after the other, through the same order definition.

This allows, for example, setting an order for 1% of the size allocated to the algorithm, and have the trading engine spawn one order per execution cycle until the 100% mark is reached. Such a feature may allow many more hacks and is yet another tool that&mdash;combined with the rest&mdash;enables a great deal of control over orders execution.

A new instance of an order may be spawned only under the following  context:

* The previous instance of the order is closed. That is, two instances of the same order may not exist at the same time.

* The size filled at the level of the execution algorithm is within the limit established in the algorithm's configuration.

* The size filled at the level of the stage must be within the target size defined under the initial targets node.

{% include note.html content="See the order's configuration to learn how to configure the parameter affecting this behavior." %}

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.content != "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.adding != "" %}

{{include.adding}} Adding {{preposition}} {{title}} Node

<!--------------------------------------------- ADDING starts -->

To add the {{ title | downcase }} node, select *Add Missing Items* on the parent node menu. 

<!--------------------------------------------- ADDING ends -->

{% endif %}

{% if include.configuring != "" %}

{{include.configuring}} Configuring the {{title}}

<!--------------------------------------------- CONFIGURING starts -->

To configure the {{ title | downcase }} node, select *Configure* on the menu. 

```json
{
     "percentageOfAlgorithmSize": 100, 
     "spawnMultipleOrders": false 
}
```

* ```percentageOfAlgorithmSize``` is the definition of how much of the size handled by the algorithm shall be allocated to this particular order. Posible values are real numbers between ```0``` and ```100```, including the extremes. If you set the value to ```0```, the order will not be executed.

* ```spawnMultipleOrders``` is the parameter that indicates whether additional spawned orders are allowed (```true```) or not (```false```).

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