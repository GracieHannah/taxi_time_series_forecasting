# Taxi Time Series Forecasting


## Project Overview

Development of a machine learning model to forecast hourly taxi demand for a taxi company. Accurate predictions help taxi companies better allocate drivers during peak hours and reduce customer wait times. Using historical taxi data, time series features such as lag variables and rolling averages were created to train and evaluate forecasting models.

---

## Business Problem

Taxi demand can fluctuate significantly throughout the day, making it difficult for companies to predict how many drivers are needed at any given time. If demand is underestimated, customers may experience longer wait times because there are not enough drivers available. If demand is overestimated, drivers may spend long periods idle, which reduces efficiency and revenue.

---

## Business Objective

By forecasting hourly taxi demand, the company can ensure that enough drivers are available during busy periods while avoiding having too many drivers during slower times. This can help reduce customer wait times, improve service reliability, and increase overall operational efficiency.

---

## Data

The dataset contains historical taxi order counts recorded at regular time intervals. The data includes timestamped records of taxi requests which are used to construct lag-based features for forecasting. 

* **'taxi.csv'** - contains two columns
    - datetime: Timestamp of the taxi order count
    - num_orders: Number of taxi orders during that time period

---

## Exploratory Data Analysis: Key Insights

* There are 4416 hours recorded rides.
* The number of rides ranging from 0 and to a max of 462 per hour
* The average number of rides per hour is 84.42
* It looks like taxi activity increases during the summer months
* 12am is the busiest time by far, with 6am being the slowest

---

## Model Development

To forecast hourly taxi demand, a machine learning time series forecasting model was developed using Python and Scikit-learn.

Key steps in the modeling process included:

* Loading historical taxi order data and converting timestamps to a datetime format
* Resampling the data to hourly intervals to create a consistent time series
* Creating lag features to capture historical demand patterns
* Generating rolling window statistics to incorporate recent trends
* Splitting the dataset into training and validation sets while preserving the time order of observations
* Training several regression models to forecast taxi demand
* Evaluating model performance using the RMSE metric to measure prediction accuracy

The model predicts the number of taxi orders for the upcoming hour, making this a time series regression problem.

---

## Model Performance

Key Results:

* Built a time series forecasting model for hourly taxi demand
* Created lag features and rolling averages to capture historical patterns
* Achieved RMSE < 48, satisfying the project accuracy requirement

---

## Practical Application

A potential workflow for implementing this forecasting model in a real-world taxi service could include:

* Collecting and storing historical taxi order data in a centralized database
* Updating the dataset regularly with new taxi order information
* Running the forecasting model at regular houry intervals to predict upcoming demand
* Using the predicted demand to estimate how many drivers should be available in different time periods
* Communicating demand forecasts to drivers or dispatch systems so they can position themselves in high-demand areas
* Monitoring actual demand compared to predictions and retraining the model periodically to improve accuracy

This workflow would allow taxi companies to make more informed operational decisions, helping improve driver allocation, reduce customer wait times, and increase overall service efficiency.
