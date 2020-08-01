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

## Documentation (Optional)
## Tests (Optional)

- Going into more detail on code and technologies used
[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber2.PNG)]()
[![INSERT YOUR GRAPHIC HERE](https://github.com/chandra20500/uber-movement/blob/master/uber3.PNG)]()

---

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
