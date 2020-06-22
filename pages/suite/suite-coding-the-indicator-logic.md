---
title:  Coding the Indicator's Logic
summary: "Learn how to use data dependencies, the variable object, and how to deal with indicators with irregular periods."
sidebar: suite_sidebar
permalink: suite-coding-the-indicator-logic.html
toc: false
---

## Main data dependency

The data building procedure works under the premise that the algorithm loops around a data collection and that&mdash;for each loop&mdash;generates a record for the product being built. For example, the SMA indicator loops around the ```candles``` product of the Candles Volumes indicator, thus, ```candles``` is the main data dependency. In the case of the ```bollingerChannels``` product, the main data dependency is the ```bollingerBands``` product of the Bollinger Bands indicator.

The main data dependency is the first dependency declared at the level of the processes. This dependency is made available in the ```record``` object, which features three properties:

* ```previous```: mainDependency.records[index - 1]
* ```current```: mainDependency.records[index],
* ```next```: mainDependency.records[index + 1]

The variable ```index``` is the index in the array of the main dependency.

For example, you may use the statement ```record.propertyName``` to access the value of any of the properties in the input datasets for the current record, or ```record.previous.propertyName``` to access the value of the property in the previous record.

{% include note.html content="The order in which dependencies are defined determines which one is the main data dependency." %}

## Multiple data dependencies

The *products* object features a property for each data dependency, and each property is named with the ```pluralVariableName``` defined in the product's configuration. Each property features an array with the dependency's data collection.

Data collections of different products may begin and end at different points in time. For example, it takes 20 candles to build the first ```bollingerBands``` object of the Bollinger Bands indicator, or 200 candles to build the first ```popularSMAs``` object of the SMA indicator. Therefore, the record in ```i``` position in the array of one product may not correspond to the same period of time of the record in the same position of a different product.

To overcome that hurdle, developers may use the ```getElement``` function, which takes two parameters:

* The name of the data collection (```pluralVariableName```) you wish to consult.

* The position in the main data dependency, for example, the tenth candle.

The function returns the record that matches the *begin* and *end* datetime of the second parameter.

For example: ```EXAMPLE CODE```

## Variable object

The output must be stored in the ```variable``` object, which is made available to record properties under the record definition node.

In the case of the data building procedure loop, the ```variable``` object may be used to retrieve records you may have stored in previous loops. Such a feature is not available in the calculations procedure loop, as the object does not persist beyond each loop in that context.


The following is an example of a procedure loop code snippet, in particular, the code that calculates the Popular SMAs product of the Simple Moving Average (SMA) indicator.

```js
/* Loop Code. */

let candle = record.current // Our main dependency is candles 
variable.last200.push(candle.close) // Add the current close value to the last 200 array.

if (variable.last200.length > 200) {
    variable.last200.splice(0, 1) // Remove the first element of the array to keep it at a maximun of 200 elements.
}

variable.sma20 = calculateSMA(20)
variable.sma50 = calculateSMA(50)
variable.sma100 = calculateSMA(100)
variable.sma200 = calculateSMA(200)

function calculateSMA(periods) {  // Having a function saves us from duplicating code.
    /* We check we have enough values to make the calculation */
    if (variable.last200.length < periods) { return 0 } // If we dont, we define the value is zero.

    let sum = 0 // Initialize sum variable. 
    for (let i = variable.last200.length - periods; i < variable.last200.length; i++) { // Iterate through the last periods
        sum = sum + variable.last200[i]
    }
    let sma = sum / periods
    return sma
}
```

{% include important.html content="Procedures may only access data up to 48 hours in the past counting from the datetime of the record being processed. For that reason, the calculation of a moving average requires temporarily storing data in an array." %}

## Irregular periods

Occasionally, a one-to-one mapping of the periods of the data dependency with the periods of the resulting product does not exist. For example, in the case of the ```bollingerChannels``` product, using the ```bollingerBands``` as the main dependency. In such a case, the algorithm may read the 1-hour ```bollingerBands``` as input but the resulting object may span several hours.

By default, the system pushes a record into the data collection for every loop. To build products that span several periods of the main dependency, you must make the *push* from within your own code.

When the system detects a push in the procedure loop code, it cancels the automatic push on each loop.