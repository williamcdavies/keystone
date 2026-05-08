---
tags:
  - CS658
---
Data mining is the non-trivial extraction of implicit, previously unknown and potentially useful information form data or the exploration & analysis, by automatic or semi-automatic means, of large quantities of data in order to discover meaningful patterns.

Data mining draws ideas from machine learning, pattern recognition, statistics, and database systems. Traditional techniques may be unsuitable due to data that is large-scale, high dimensional, heterogeneous, complex, or distributed.

Data mining tasks can be divided into two categories: prediction methods (use some variables to predict unknown or future values of other variables) and description methods (find human-interpretable patterns that describe the data).

## What is Data?
Data is a collection of data objects (objects are also known as records, points, cases, samples, entities, or instances) and their attributes (attributes are also known as variables, fields, characteristics, dimensions, or features).

## Attributes
There are different types of attributes:
- Nominal: ID numbers, eye colours, zip codes. Nominal attributes possess distinctness ($=, \neq$).
- Ordinal: rankings (e.g., tase of potato chips on a scale from $1 - 10$), grades, height in {tall, medium, short}. Ordinal attributes possess distinctness and order ($<, >$).
- Interval: calendar dates, temperatures in Celsius or Fahrenheit. Interval attributes possess distinctness, order, and addition ($+, -$).
- Ratio: temperature in Kelvin, length, time, counts. Ratio attributes possess distinctness, order, addition, and multiplication ($\times, \div$).

## Descriptive Data Mining 
Descriptive mining is used to generate correlation, cross-tabulation, frequency, and other similar results. These methods are dedicated to uncovering patterns and finding regularities in data.

### Clustering Analysis
Clustering analysis is the process of determining which data sets are similar to one another. For example, to increase conversion rates, clusters of customers with similar buying habits can be grouped together with similar products.

### Summarisation Analysis
Summarisation analysis is the process of determining which data sets are similar to one another. For example, summarising a large number of items related to Christmas season sales provides a general description of the data, which can be extremely useful to sales and marketing managers.

### Association Rules Analysis
Association rules analysis aids in the discovery of interesting relationships between various variables in large databases. The retail industry is the best example, As the holiday season approaches, retail stores stock up on chocolates, with sales increasing before the holiday, which is accomplished through data mining.

### Sequence Discovery Analysis
Sequence discovery analysis is all about how to do something in a specific order. For instance, a user may frequently purchase shaving gel before purchasing a razor in a store. It all comes down to the order in which the user purchases the product, and the store owner can then arrange the items accordingly.

## Predictive Data Mining
Predictive data mining is used to predict future outcomes rather than current behaviour. It predicts the target value using supervised learning functions.

### Classification Analysis
Classification analysis is used to retrieve critical and pertinent data and metadata. It categorises information into various groups. Classification analysis is best demonstrated by email providers. They use algorithms to determine whether or not a message is legitimate. 

### Regression Analysis
Regression analysis tries to express the interdependence of variables. Forecasting and prediction are common applications.

### Time Serious Analysis
Time serious analysis is a series of well-defined data points taken at regular intervals.

### Prediction Analysis
Prediction analysis is related to time series, but the time isn't restricte.