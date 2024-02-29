**Predicting bike usage in Paris**
===
### Why?

Since the COVID-19 pandemic, the usage rate of bikes as a mode of commute in Paris has increased significantly. 
While the City of Paris has implemented many new bike lanes to make cycling around Paris safer and more ergonomic, there are times where the bike traffic on certain streets is congested.

Personally, as a bike-user in Paris, I have found navigating some streets where the traffic is very busy to be frustrating and slow, and make me feel unsafe. 

### What?

To help commuters decide which mode of transport to take (i.e. bike, walk, metro, bus, etc...) or even whether or not they should work in-office, or remotely, we aim to predict the traffic of bikes in Paris to give an indication of what a commuter's experience will be like on a given day at a given time. 

### How?

The City of Paris provides many different public APIs and datasets for anyone to use, including urban projects, environmental data, demographics, public services, and traffic information; specifically, among other things, the traffic of bikes counted per hour. 

Using past traffic data, along with external factors, such as past weather data and forecasts, we hypothesise that trends will be apparent, and that we will be able to forecast future traffic trends using a machine-learning algorithm. 

The data was made available by OpenData Paris, found here: [Paris | Data][1]

**Conclusion 

While the algorithm can more or less accurately predict the peaks of bike traffic in Paris, it would benefit from more data to be able to analyse the seasonality year-to-year.

There are other external factors that likely impact bike traffic in Paris. If we use these factors to tune our algorithm further, this may improve accuracy.

To further tune the algorithm, we could consider:

Temperature forecasts -- Cyclists may decide to work remotely or take public transport when the weather is very cold or very hot
Planned public transport closures and strikes -- Parisiens may be obliged to commute by bike when metro lines are closed for works
The price of petrol?

Going further, we could consider creating an application that automatically calls the OpenData Paris API, cleans the data and runs the algorithm on a regular basis to provide predictions for day n+x.

We can see two main challenges with this project at this stage: 
1. In order to provide correctly formatted data to the algorithm, we would need to automatically clean the data and account for things like outliers or data collection errors due to material faults or similar.  Initially, this project used data from 2021, but we can see that if we plug in data from 2023, the data cleaning functions break at some point.  It would be challenging to account for all possible data collection errors, therefore we foresee regular and considerable maintenance costs.

2. As we have concluded, the predictions could benefit from more data. However, it seems that the data hosted by OpenData Paris doesn't persist after ~12-18 months.  A solution could be to initialise a database containing the results of the machine learning algorithm, which is then alimented over time. 

[1]: https://opendata.paris.fr/explore/dataset/comptage-velo-donnees-compteurs/information/?disjunctive.id_compteur&disjunctive.nom_compteur&disjunctive.id&disjunctive.name
