# Projecting Batted Ball Outcome using Machine Learning 
Leveraging Statcast baseball data to predict the likelihood of a successful hit using machine learning models. 

## Overview
This project explores the use of machine learning to predict batted ball outcomes in baseball. Utilizing Statcast data, the goal 
is to determine the likelihood of a successful hit based on launch angle, exit velocity, and spray angle. 
The project employs Python and popular data science libraries to develop and evaluate a predictive model.

---

## Gathering and Preparing Data
Statcast data is available to the public for free using [BaseballSavant.com](https://baseballsavant.mlb.com/statcast_search). Fans can create their own queries and view results on the website or download csv files. With the help of the [pybaseball](https://github.com/jldbc/pybaseball) library, we can use Python to easily scrap data from Baseball Savant. 

The following [attributes](https://baseballsavant.mlb.com/csv-docs) are collected from our query: 
 - ```stand``` : Side of the plate batter is standing. 
 - ```launch_angle``` : Launch angle of the batted ball.
 - ```launch_speed``` : Exit velocity of the batted ball. 
 - ```hc_x``` : Hit coordinate X of batted ball.
 - ```hc_y``` : Hit coordinate Y of batted ball.
 - ```events``` : Event of the resulting Plate Appearance. 

Although Baseball Savant doesn't directly provide us with spray angle, using a formula created by [Bill Petti](https://tht.fangraphs.com/research-notebook-new-format-for-statcast-data-export-at-baseball-savant/), we can find it using the ```hc_x``` and ```hc_y``` attributes.  

```python
data.hc_x = (data.hc_x - 125.42)
data.hc_y = (198.27 - data.hc_y)
spray_angle = np.round(np.arctan(data.hc_x / data.hc_y) * 180 / np.pi * 0.75)
spray_angle[data['stand'] == 'L'] *= -1 # spray angle is dependent on the hitter's handedness
data['spray_angle'] = spray_angle
```





---

## Requirements
The following libraries are used throughout the project:

---

## Setup using Google Colab
1. Using the menu bar at the top of the page, select: File -> Upload Notebook -> GitHub
 ``` 
 https://github.com/susconnor/Hit-Projector.git
 ```

2. Under Path select ```Hit_Projector.ipynb ```

3. Runtime -> Run all

## Acknowledgments
- This project makes use of the [pybaseball](https://github.com/jldbc/pybaseball) library, developed by [James LeDoux](https://github.com/jldbc) and contributors. It provides an easy interface for accessing Statcast data and other baseball statistics.   

