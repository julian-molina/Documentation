---
title:  Runtime Cycle
summary: "When running on a data mining operation, indicators follow a cycle designed to fulfill their purpose: to process data others have produced and make the result available for others to consume."
sidebar: suite_sidebar
permalink: suite-runtime-cycle.html
---

Indicators take datasets produced by sensors or by other indicators as input. These inputs are determined by the data dependencies defined. The calculations procedure and the data building procedure produce the intended transformations. The data building procedure stores the results in datasets that others may use as input, and the calculations procedure may make certain pieces of information available without ever writing it in the files.

The following is the breakdown of the cycle.

## 1. Loading of data dependencies

Datasets produced by indicators are sets of text files with data stored in the form of arrays. Each value in a record is separated by colons, and each record is delimited by square brackets. Records are too separated by colons. The format in which data is stored in files aims to make files as lightweight as possible.

For example, the following fragment features three records in the 24-hours Multi-Period-Market Bollinger Bands ```Data.json``` file:

```
... ,[1586044800000,1586131199999,6339.464,440.8934655492186,881.7869310984372],[1586131200000,1586217599999,6440.327,424.9041072418576,849.8082144837152],[1586217600000,1586303999999,6530.541,382.3824677453191,764.7649354906382], ...
```

That is what the system encounters at the time of reading a typical file in a dataset, which is the first step in the runtime cycle.

## 2. Transformation of files into JSON objects with named properties

Once a file is loaded in memory, it is inflated into a JSON object structure, with named properties. This is the second step in the cycle and aims to make accessing each record&mdash;from within the code&mdash;much easier.

## 3. Calculation of properties not stored in the dataset

Because performance is inversely related to the weight of files, developers may choose not to store all indicator properties in files. They may choose to leave properties that are easy to calculate out of the dataset and make them available as calculated properties instead. Calculated properties are calculated by the calculations procedure and fed to the record definition formulas to be made available as an integral part of the object other indicators may access.

For example, picture an indicator that offers buy, sell, and total volumes. Because the total volume is so easy to calculate, the developer of such an indicator may choose to store the buy and sell volumes only and make the total volume available as a calculated property.

Let's consider another example. Let's say a developer wishes the indicator to provide the direction in which the price is moving, based on a moving average. Instead of storing ```"Up"``` or ```"Down"``` for the value of the ```direction``` property, the developer may choose to store ```0``` and ```1``` respectively, and use the calculations procedure to map the value ```0``` with ```"Up"``` and ```1``` with ```"Down"```, saving considerable weight in the files.

{% include tip.html content="Make your indicators more efficient by limiting the amount of information you store in files." %}

The third step in the runtime cycle is, therefore, to run the calculations procedure of each data dependency and add the calculated properties to the JSON object structure in memory, so that all properties are available for the next steps in the cycle.

## 4. Products structure

Steps 1, 2, and 3 are run for each one of the data dependencies, and the results are put inside an object named ```products```. In this way, all data dependencies may be easily accessed with the following kind of syntax:

```products.pluralVariableName[index].property```

For example: ```products.bollingerBands[10].deviation```

Each product remains an array of JSON objects with named variables.

## 5. Transformations

The fifth step in the runtime cycle is running the indicator's data building procedure. This is where the developer codes the logic to go over the input datasets and perform the calculations required to produce the indicator's output.

Indicators may have multiple products, thus, the data building procedure corresponding to each product is run sequentially, in the order products have been defined around the indicator bot node. 

As transformations for a given product are finished, the results are appended to the products object and made available immediately for the rest of the products in the queue to use as input, in addition to the original data dependencies. Data dependencies are the same for all products, as data dependencies are defined at the level of processes.

## 6. Writing the output

The final step is turning the object-formatted records back into a minimized array format, and saving the corresponding files in the dataset.