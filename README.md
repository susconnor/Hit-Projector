# Projecting Batted Ball Outcome using Machine Learning 
Leveraging Statcast baseball data to predict the likelihood of a successful hit using machine learning models. 

## Overview
This project explores the use of machine learning to predict batted ball outcomes in baseball. Utilizing Statcast data, the goal 
is to determine the likelihood of a successful hit based on launch angle, exit velocity, and spray angle. 
The project employs Python and popular data science libraries to develop and evaluate a predictive model.

---

## Gathering and Preparing Data
Statcast data is available to the public for free using [BaseballSavant.com](https://baseballsavant.mlb.com/statcast_search). Fans can create their own queries and view results on the website or download csv files. With the help of the [pybaseball](https://github.com/jldbc/pybaseball) library, we can use Python to easily scrap data from Baseball Savant.




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

