<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "Check the Integrity of Your Data" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about the {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

Your PC may have been forcefully shut down or you may have closed the console running the Superalgos backend while running a data-mining operation. Such situations may cause some data to become corrupt.

**1. Check the integrity of the sensor bot data**

Go to the ```Exchange-Raw-Data``` folder under ```Data-Storage > Exchange > Market > Masters``` and keep opening the subfolders to get to the last day available, and open the ```Data.json``` file. If the file opens fine, this may mean that the data you downloaded from the exchange is safe.

If the last file in ```Exchange-Raw-Data``` does not open properly then delete the whole ```Data-Storage > Exchange > Market``` and run the data mining operation. This will have the OHLCV sensor bot download all the data from the exchange again, and all indicators calculated from scratch.

If the sensor data seems fine, then proceed with the next step.

**2. Check the integrity of indicator's data**

If you are having issues with candles you need to check the data of the Candles Volumes indicator of the Masters Data Mine located deep in ```Multi-Period-Daily``` and ```Multi-Period-Market``` folders under ```Data-Storage > Exchange > Market > Masters > Candles-Volumes > Output > Candles```.

If you find any ```.tmp``` files or you can't open some of the latest ```Data.json``` files in a regular text editor, or some files are empty, chances are the files have been corrupted.

{% include note.html content="Something similar may have happened with other indicators as well, so make sure you check the data storage folders of indicators that may not be working or that you may be experiencing issues with." %}

If that is the case, then you will delete the folder for each data mine within ```Data-Storage > Exchange > Market```, but will leave ```Exchange-Raw-Data``` intact, and get the data mining operation running afterward. This will regenerate all indicators data products, including Candles Volumes.

**3. Remember that there is a proper way to close the system!**

{% include /how_to/safely-close-superalgos.md heading="more" definition="yes" content="yes" extended="no" table="yes" more="yes"%}

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