# Winning-Space-Race-With-Data-Science


![tumblr_lo0uhsu5IC1qhp3olo1_500](https://user-images.githubusercontent.com/86102231/147546030-15970711-052f-43f9-a398-00ee8cdbac40.gif)
 

### Date: 12 th of October 2021  


## Author : [GAURAB KUNDU](https://www.linkedin.com/in/gaurab-kundu-020803) 

# Project Description

In this project, we will predict if the Falcon 9 first stage will land successfully. SpaceX advertises Falcon 9 rocket launches on its website, with a cost of 62 million dollars; other providers cost upward of 165 million dollars each, much of the savings is because SpaceX can reuse the first stage. Therefore if we can determine if the first stage will land, we can determine the cost of a launch. This information can be used if an alternate company wants to bid against SpaceX for a rocket launch.


# Outline 

|       SL. NO        |                                    Outline                                      |
| :-----------------: | :-----------------------------------------------------------------------------: |
|          1          |                              [Executive Summary](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/README.md#executive-summary)                                 |
|          2          |                                 [Introduction](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/README.md#introduction)                                    |
|          3          |                                   [Objective](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/README.md#objective)                                     |
|          4          |                       [Hardware and Software Requirments](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/README.md#hardware-and-software-requirments)                         |
|          5          |                                  [Methodology](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/README.md#methodology)                                    |
|          6          |                  [Insights Drawn from Exploratory Data Analysis](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/README.md#insights-drawn-from-exploratory-data-analysis)                  |
|          7          |                        Launch Sites Proximities Analysis                        |
|          8          |                       Build A Dashboard with Plotly Dash                        |
|          9          |                       Predictive Analysis Classification                        |
|          10         |                                  Conclusion                                     |


# Executive Summary

The project is focused on collecting data by web scrapping or API calls, perform EDA and visualize the data before building a classification machine learning models to predict whether the landing will succeed or not.

The results are the plots that show relation of two variables, dashboard, map, and the best classification model is decision tree to predict first stage will be successful or not.


# Introduction

In the age of commercial space travelling, SpaceX advertises Falcon 9 rocket launches on its website with a cost of 62 million dollars; other providers cost upward of 165 million dollars each, much of the savings is because SpaceX can reuse the first stage.
In this Data Science project we will predict if the Falcon 9 first stage will land successfully, therefore if we can determine if the first stage will land, we can determine the cost of a launch. This information can be used if an alternate company wants to bid against SpaceX for a rocket launch.


# Objective

## Background
 Reviewing Space X's success in making Falcon 9 rockets with very minimum costs.

 We can analyze SpaceX's data to get the minimum cost to launch a successful rocket for our company.
## Problem
 Predicting whether the first stage land bases on features given.

 Analyzing the features that affect landing success.
## Question for Analysis
 Will the first stage land based on features given?

 Will the features affect landing success?


# Hardware and Software Requirments

## Hardware
In this Project We are going to use IBM Cloud Pack for Data and its various Web services, so a RAM of 8 GB and decent Internet Connection is required only. All the hardware requirments will be covered by IBM Cloud Pack for Data. 
## Software
We are going to use IBM Watson Studio for this project.

In case of local machine We are going to use the following softwares in this project :

Programming Language : [Python](https://www.python.org/)

IDE : [Jupyter Notebook](https://jupyter.org/)

Packages : [Pandas](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html), [Numpy](https://numpy.org/), [Scipy](https://scipy.org/), [Scikit-learn](https://scikit-learn.org/stable/), [Matplotlib](https://matplotlib.org/), [BeautifulSoop](https://pypi.org/project/beautifulsoup4/).


# Methodology

## Data Collection
The data set used in the project is the [SpaceX Launch data](https://drive.google.com/file/d/1JsDQrujo-qdQPMIdjkXmkzmN8xQIQRig/view?usp=sharing).

The data set contains information about different flights including date, launch site, booster version and more.

The data is collected by two main approaches:

1. The SpaceX API

2. Web Scrapping

### Data Collection – SpaceX API

We’ll be collecting launch data from SpaceX API, First we request launch data from SpaceX API using the GET command (requests.get), then we create a pandas dataframe from the response, After that we make several sub requests to get more detailed and consistent information about the IDs stored in the dataframe. 

With the help of some helper functions, we save the responses into a dictionary, and then we transform it into a dataframe, which is our data set.

 ![Screenshot (159)](https://user-images.githubusercontent.com/86102231/147389192-9446f2a8-80db-468a-afcf-1de89a327010.png)

### To see the code and step by step process of Data Collection using SpaceX API [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%201/Data%20Collection/jupyter-labs-spacex-data-collection-api.ipynb)

### Data Collection - Web Scrapping

We will be performing web scraping to collect Falcon 9 historical launch records from a Wikipedia page. First we perform an HTTP GET( using requests.get command)method to request the Falcon9 Launch HTMLpage, as an HTTP response. Then we create a BeautifulSoup object from the HTML response, We extract the column names from the object and use it
as dictionary keys.

We parse the HTML tables and fill the dictionary keys with launch records from table rows, and finally we transform it into a dataframe.

![Screenshot (161)](https://user-images.githubusercontent.com/86102231/147544733-7e925792-5529-4667-8c49-2509f6d53313.png)

### To see the code and step by step process of Data Collection with Web Scrapping [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%201/Data%20Collection/webscrapping.ipynb)

## Data Wrangling

Exploratory data analysis is an important step while preprocessing data, it is useful to find some patterns in the data and determine what would be the label for training supervised models.

This process was done in the following order:

1. First thing to do is to identify the data types of the columns.

2. Determine the number of values for each attribute.

3. Calculate the percentage of the missing values.

4. To determine the label, weapply zero/one hot encoding to the “Outcome” column to classify landing to either 1(Success) of 0 (Failure)

### To see the code and step by step process of Data Wrangling [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%201/Data%20Wrangling/labs-jupyter-spacex-Data%20wrangling.ipynb)

## EDA with SQL 

In order to better understand the datasets, we ran the following SQL queries:

1. Display the names of the unique launch sites in the space mission.

2. Display 5 records where launch sites begin with the string 'CCA'.

3. Display the total payload mass carried by boosters launched by NASA (CRS).

4. Display average payload mass carried by booster version F9 v1.1 .

5. List the date when the first successful landing outcome in ground pad was achieved.

6. List the names of the boosters which have success in drone ship and have payload mass greater than 4000 but less than 6000.

7. List the total number of successful and failure mission outcomes.

8. List the names of the booster versions which have carried the maximum payload mass. Use a subquery.

9. List the failed landing outcomes in drone ship, their booster versions, and launch site names for in year 2015.

10. Rank the count of landing outcomes (such as Failure (drone ship) or Success (ground pad)) between the date 2010-06-04 and 2017-03-20, in descending order.

### To see the code and step by step process of EDA With SQL [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%202/Exploratory%20Analysis%20Using%20SQL/jupyter-labs-eda-sql-coursera.ipynb)

## EDA with Data Visualization

In order to understand the relations between different features, we visualize the data by plotting scatter plots, bar charts and line charts, it helps finding hidden patterns in data and gain insights about the dataset.

1. Pay load mass against the Flight number.

2. Lunch site against the Flight number.

3. Lunch site against the Pay load mass.

4. Orbit type against Class success rate.

5. Flight number against Orbit type.

6. Orbit type against the Pay load mass.

7. launch success yearly trend.

### To see the code and step by step process of EDA with Data Visualization [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%202/Exploratory%20Analysis%20Using%20Pandas%20and%20Matplotlib/jupyter-labs-eda-dataviz.ipynb)

## Build an Interactive Map with Folium

Here, we complete the interactive visual analytics using Folium.

First we create Folium map object, with an initial center location around Nasa Johnson space center, Houston-Texas.

 We add a circle on the map for each launch site from the dataset by creating a folium circle and folium marker, now the launch sites are marked on the map which means we can see which one is proximate to the equator line or close to a coastline.

 In order to mark the success/failure launches, we create a marker on the map for each launch record from the dataset, a green marker indicates a successful lunching and a red one indicates failure,

we need to explore and analyze the proximities of launch sites, we calculate the distance between the launch site and its proximities and then we draw a polyline between them.

To see the code and step by step process of Build an Interactive Map with Folium [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%203/Interactive%20Visual%20Analytics%20and%20Dashboard/lab_jupyter_launch_site_location.ipynb)

## Predictive Analysis (Classification)

Now that we finished the exploratory analysis, the next step is to determine the training labels and build a predictor using machine learning algorithms. After using the ‘Class’ column as the label, first thing to do is normalizing the data. We split the normalized data into test/train sets, The training data is divided into validation data, a second set used for training data.

For the model development phase, we use the following algorithms:

1. Logistic regression

2. Support vector machine

3. Decision trees

4. K nearest neighbor

We build a grid search object for each of the algorithms and f i t it to find the best parameters of the model(hyper parameters tuning), then we choose the most accurate model.

To see the code and step by step process of Predictive Analysis (Classification) [CLICK HERE](https://github.com/GaurabKundu1/IBM-Data-Science-Professional-Certificate-Capstone-Project-Winning-Space-Race-With-Data-Science/blob/main/Week%204/Predictive%20Analysis%20(Classification)/SpaceX_Machine%20Learning%20Prediction_Part_5.ipynb)

## Results

Success rate increased noticeably from 2013 and on.

Launch site and the orbit type are the features with the largest effect on the outcome.

KNN and SVM models have a validation set accuracy of 83% and an out of sample accuracy of 77%.

# Insights Drawn from Exploratory Data Analysis

## Flight Number vs. Launch Site



## Payload vs. Launch Site



## Success Rate vs. Orbit Type



## Flight Number vs. Orbit Type



## Payload vs. Orbit Type



## Launch Success Yearly Trend



## All Launch Site Names



## Launch Site Names Begin with 'CCA'



## Total Payload Mass



## Average Payload Mass by F9 v1.1



## First Successful Ground Landing Date



## Successful Drone Ship Landing with Payload between 4000 and 6000



## Total Number of Successful and Failure Mission Outcomes



## Boosters Carried Maximum Payload



## 2015 Launch Records



## Rank Landing Outcomes Between 2010-06-04 and 2017-03-20



# 
