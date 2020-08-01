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
- [data Collecting](#data_Collecting)
- [EDA](#EDA)
- [preparing data for model](#data_preparation)
- [Applying model](#model_preparation)
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

## data_Collecting

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

## data_preparation
- To prepare data to train our MLmodel we must make sure that our datasethave all the suitable columns i have destinationID,sourceID and distance between centroid of two wards as independent variable and average travel time as dependent variable.
- To get distance between two centroids we are going to make a 2D matrix where cell say A[i][j] will have distance between two points which is diagonal distance between those    two points so it dosen't matter weather it is from i to j or j to i.
-image below shows a sample example of such 2D matrix where distance between centroids is stored.

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber8.PNG)]()

- further we have to create a database with average travel time sourceID, destinationID, distance and average travel time.

[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber9.PNG)]()

> And our Dataset is ready to use.
## Tests (Optional)


## Contributing

> To get started...

### Step 1

- **Option 1**
    - 🍴 Fork this repo!

- **Option 2**
    - 👯 Clone this repo to your local machine using `https://github.com/joanaz/HireDot2.git`

### Step 2

- **HACK AWAY!** 🔨🔨🔨

### Step 3

- 🔃 Create a new pull request using <a href="https://github.com/joanaz/HireDot2/compare/" target="_blank">`https://github.com/joanaz/HireDot2/compare/`</a>.

---

## Team

> Or Contributors/People

| <a href="http://fvcproductions.com" target="_blank">**FVCproductions**</a> | <a href="http://fvcproductions.com" target="_blank">**FVCproductions**</a> | <a href="http://fvcproductions.com" target="_blank">**FVCproductions**</a> |
| :---: |:---:| :---:|
| [![FVCproductions](https://avatars1.githubusercontent.com/u/4284691?v=3&s=200)](http://fvcproductions.com)    | [![FVCproductions](https://avatars1.githubusercontent.com/u/4284691?v=3&s=200)](http://fvcproductions.com) | [![FVCproductions](https://avatars1.githubusercontent.com/u/4284691?v=3&s=200)](http://fvcproductions.com)  |
| <a href="http://github.com/fvcproductions" target="_blank">`github.com/fvcproductions`</a> | <a href="http://github.com/fvcproductions" target="_blank">`github.com/fvcproductions`</a> | <a href="http://github.com/fvcproductions" target="_blank">`github.com/fvcproductions`</a> |

- You can just grab their GitHub profile image URL
- You should probably resize their picture using `?s=200` at the end of the image URL.

---

## FAQ

- **How do I do *specifically* so and so?**
    - No problem! Just do this.

---

## Support

Reach out to me at one of the following places!

- Website at <a href="http://fvcproductions.com" target="_blank">`fvcproductions.com`</a>
- Twitter at <a href="http://twitter.com/fvcproductions" target="_blank">`@fvcproductions`</a>
- Insert more social links here.

---

## Donations (Optional)

- You could include a <a href="https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.png" target="_blank">Gratipay</a> link as well.

[![Support via Gratipay](https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.png)](https://gratipay.com/fvcproductions/)


---

## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
- Copyright 2015 © <a href="http://fvcproductions.com" target="_blank">FVCproductions</a>.
