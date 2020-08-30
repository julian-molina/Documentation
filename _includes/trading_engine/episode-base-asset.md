<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Episode Base Asset" %}
{% assign definition = site.data.trading_engine.episode_base_asset %}
{% assign preposition = "an" %}
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

Because the system aims to be as flexible as possible, the trading engine keeps the accounts relative to both the base asset and the quoted asset. This allows the user to set up the trading system with whatever logic is required and decide which set of accounts suits the intent&mdash;the goal&mdash;of the trading strategy.

{% include callout.html type="success" content="Notice that&mdash;usually&mdash;the accounts denominated in one asset will be valid, while the accounts denominated in the other asset will likely make no sense." %}

Which set of accounts you will monitor to track the performance of the episode depends on how you define your trading system. 

For example, If you are trading the BTC/USDT market and developed a trading system to accumulate USDT, then the set of accounts that will make sense for you is the one denominated in the quoted asset, that is, in USDT. This is why:

Your strategy will likely buy BTC (the base asset) expecting the price to go up while the position is open, in order to sell BTC at a higher rate and end up with more USDT (the quoted asset) than you started with. 

*Let's put a simple example in numbers:*

Let's say you buy 10,000 USDT worth of BTC. BTC price increases by 10%, so you sell the whole amount of BTC to close the position and end up with 10,900 USDT *(exchange fees are deducted from the balance)*.

In terms of the base asset, your begin balance is 0 BTC and your end balance is 0.00000012 BTC, as the exchange left some BTC dust in the account due to rate conversion limitations. Also in terms of the base asset, your profit loss for the position is ```0.00000012 BTC - o BTC = 0.00000012 BTC```. ROI and other metrics may be derived from these initial observations as well. Needless to say, such metrics are irrelevant to the intent of the strategy, which is to accumulate USDT.

Now, in terms of the base asset, your begin balance is 10,000 USDT and your end balance is 10,900 USDT *(exchange fees are deducted from the balance)*. Also in terms of the quoted asset, your profit loss for the position is ```10,900 USDT - 10,000 USDT = 900 USDT```. It should be clear by now that these are the metrics relevant to the intent of the strategy.

{% include note.html content="With other types of strategies, for example, those in which the intent is to accumulate both assets, both sets of metrics may be relevant. Also, the consolidated metrics provided in the context of statistics may be relevant too." %}

{% include tip.html content="On the charts, find the metrics for both the episode base asset and episode quoted asset under the *Episode* layer within the *Trading Charts* layer manager. " %}

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