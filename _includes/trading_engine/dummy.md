<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Trading Engine" %}
{% assign definition = site.data.trading_engine.trading_engine %}
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

You will use this hierarchy for two main purposes:

The hierarchy exposes&mdash;literally&mdash;all the information processed by the trading bot, providing a comprehensive feedback loop to trading systems and analysis capabilities to users. The hierarchy exposes&mdash;literally&mdash;all the information processed by the trading bot, providing a comprehensive feedback loop to trading systems and analysis capabilities to users.

* **To let your trading systems:** This allows strategies to keep track of and react to current and past events&mdash;including those involving the exchange, such as orders placed or filled&mdash;as the bot is running.

* **To keep track of the actions:** By analyzing runtime information, you may gain a detailed understanding of what happens, when, and why, throughout a trading session.

The hierarchy exposes&mdash;literally&mdash;all the information processed by the trading bot, providing a comprehensive feedback loop to trading systems and analysis capabilities to users.

{% include callout.html type="success" content="Este callout se usa para resaltar una idea particularmente importante. Algo se sobresale, como una conclusion, o algo por el estilo." %}

The hierarchy exposes all the information processed by the trading bot, providing a comprehensive feedback loop to trading systems and analysis capabilities to users. The hierarchy exposes all the information processed by the trading bot, providing a comprehensive feedback loop to trading systems and analysis capabilities to users.

{% include note.html content="Esto es una nota, algo noteworthy." %}

{% include tip.html content="Esto es un tip." %}

{% include important.html content="Esto es algo importante." %}

{% include warning.html content="Esto es una aviso de alerta." %}

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.content != "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.adding != "" %}

{{include.adding}} Adding {{preposition}} {{title}} Node

<!--------------------------------------------- ADDING starts -->

Calculo que con este segundo nivel de titulo alcanza.

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