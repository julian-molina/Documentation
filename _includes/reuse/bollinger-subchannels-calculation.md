<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Bollinger SubChannels Calculation" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about the {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

**Direction:**

* ```Down```: ```previous.bollingerBand.movingAverage > bollingerBand.movingAverage```

* ```Up```:  ```previous.bollingerBand.movingAverage < bollingerBand.movingAverage```

* ```Side```: ```previous.bollingerBand.movingAverage === bollingerBand.movingAverage```

**Slope:**

The following variable is calculated first:

```variable.delta = bollingerBand.movingAverage - previous.bollingerBand.movingAverage```

Then, the range of slopes is divided into four arbitrary segments:

```variable.SIDE_TOLERANCE = 0.5 * system.timeFrame / system.ONE_DAY_IN_MILISECONDS```

```variable.SMALL_SLOPE = 1.0 * system.timeFrame / system.ONE_DAY_IN_MILISECONDS```

```variable.MEDIUM_SLOPE = 2.0 * system.timeFrame / system.ONE_DAY_IN_MILISECONDS```

```variable.HIGH_SLOPE = 4.0 * system.timeFrame / system.ONE_DAY_IN_MILISECONDS```

Finally, a coloquial name is assigned to the slope property given by the range in which the ```variable.delta``` falls into:

* ```Side```: ```variable.delta < bollingerBand.movingAverage * variable.SIDE_TOLERANCE / 100```

* ```Gentle```: ```variable.delta < bollingerBand.movingAverage * variable.SMALL_SLOPE / 100``` <br />*(and greater than "Side")*

* ```Medium```: ```variable.delta < bollingerBand.movingAverage * variable.MEDIUM_SLOPE / 100``` <br />*(and greater than "Gentle")*

* ```Steep```: ```variable.delta < bollingerBand.movingAverage * variable.HIGH_SLOPE / 100``` <br />*(and greater than "Medium")*

* ```Extreme```: *Greater than "Steep".*


<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.extended == "more" and include.content != "more" %}
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