# UBER Movement data

<a href="http://fvcproductions.com"><img src="https://miro.medium.com/max/875/1*xCeJKwAwPJNPpRBEjp68oQ.jpeg" title="trafic image" alt="trafic image"></a>

> Travel timeprediction 

> Using Uber movement data to predict travel time  

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber1.PNG)]()

- i have used data of bengaluru which can be easily downloded from https://movement.uber.com/
- downloded hourly aggregated data and bangloe_wards.json file for geograpic operations 
---

## Table of Contents 

- [Installation](#installation)
- [Data collection](#Data collection)
- [EDA](#EDA)
- [Preparing data for model](#Preparing data for model)
- [Applying model](#Applying model)
- [Result](#Result)

---

## Example (Optional)

```Python
// code away!

let generateProject = project => {
  let code = [];
  for (let js = 0; js < project.length; js++) {
    code.push(js);
  }
};
```

---

## Installation

- !pip install PyDrive 
- !pip install geopandas
- !pip install shapely

## Data collection

> first of all we have to inport our csv and json file from google drive.
https://buomsoo-kim.github.io/colab/2018/04/16/Importing-files-from-Google-Drive-in-Google-Colab.md/
follow this url for step by step processing. 

## EDA
- EDA is very important when it comes to understanding data that we have 
- first of all we are going to visualise data from csv file only
- A plot of average average travel time for different hour

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber2.PNG)]()
- now to have a better understanding of travel time variation for different time we have selected two random wards giri nagar and malleswaram and plot below describe when 
is the most suitable and non suitable time to travel 

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber3.PNG)]()

- Next moving to our Json file
- Just to get starting with geopandas

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber4.PNG)]()

- Now i have picked a time(6PM evening) and a spot Lingarajapura in ward number 49 now we are going to see where i can react in less than half an hour

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber5.PNG)]()

- going further lets see where we can reach in , >30min (#2b8cbe), 20min - 30min (#7bccc4) , 10min - 20min (#bae4bc) and < 10min (#f0f9e8) in plot below i have plotted lingarajpuram with red color

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber6.PNG)]()

- Next lets plot centroid of all these wards these points are going to help us in predicting average travel time

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber7.PNG)]()

## Preparing data for model
- To prepare data to train our MLmodel we must make sure that our datasethave all the suitable columns i have destinationID,sourceID and distance between centroid of two wards as independent variable and average travel time as dependent variable.
- To get distance between two centroids we are going to make a 2D matrix where cell say A[i][j] will have distance between two points which is diagonal distance between those    two points so it dosen't matter weather it is from i to j or j to i.
-image below shows a sample example of such 2D matrix where distance between centroids is stored.

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber8.PNG)]()

- further we have to create a database with average travel time sourceID, destinationID, distance and average travel time.

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber9.PNG)]()

> And our Dataset is ready to use.
## Applying model

> i am using Gradient Boost for this dataset
> but first of all lets split our dataset into train and test set
---
```Python
df_train, df_test = train_test_split(x, train_size = 0.8, test_size = 0.2, random_state = 100)
```
---
> now splitting training dataset into x_train (independent variable) and y_train (dependent variable)
---
```Python
y_train = df_train.pop('mean_travel_time')
X_train = df_train

y_test = df_test.pop('mean_travel_time')
X_test = df_test
```
---
> Now lets train our model 
---
```Python
from sklearn.ensemble import GradientBoostingRegressor
regressor = GradientBoostingRegressor(n_estimators = 150,
                                         max_depth = 2,
                                         min_samples_split = 20,
                                         learning_rate = 0.38,
                                         loss = 'ls')
# fit the regressor with x and y data 
regressor.fit(X_train, y_train)
```
---

> Now lets make a prediction
---
```Python
y_pred = regressor.predict(X_test)
```
---

## Result

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber10.PNG)]()
