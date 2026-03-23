Store Sales - Time Series Forecasting

This project aims to predict grocery sales for Corporation Favorita, a large Ecuadorian-based grocery retailer, using time-series forecasting techniques. The dataset is sourced from the Kaggle Store Sales Competition.

Project Overview

The goal is to build a model that more accurately predicts the unit sales for thousands of items sold at different Favorita stores. This notebook demonstrates a complete workflow from data loading and cleaning to feature engineering and predictive modeling.

Data Description

The primary dataset used is train.csv, which contains the following key columns:

id: Unique identifier for each record.
date: The date of the sales record.
store_nbr: Identifies the store at which the products are sold.
family: Identifies the type of product sold.
sales: The total sales for a product family at a particular store at a given date. (Target Variable)
onpromotion: The total number of items in a product family that were being promoted at a store at a given date.
Workflow

1. Data Cleaning & Preparation

Date Parsing: Converted the date column to datetime objects. Handled malformed strings (e.g., '2013-05-') by coercing them to NaT and removing them to ensure data integrity.
Aggregation: Grouped sales by date to analyze total daily business demand.
2. Feature Engineering

To improve the model's ability to capture seasonality and trends, the following features were engineered:

Time Features: Year, Month, Day, and Day of the Week.
Lag Features: Created Sales_Lag1 to represent the sales from the previous day, which is a strong indicator in time-series data.
3. Exploratory Data Analysis (EDA)

Visualized monthly sales trends using Plotly to identify peak seasons and potential data gaps.
4. Predictive Modeling

Model: Random Forest Regressor.
Training: Used an 80/20 temporal split (no shuffling) to respect the time-series nature of the data.
Evaluation: The model achieved a Mean Absolute Error (MAE) of $30,652.10 on the test set.
5. Visualization

Generated a comparison plot of 'Actual Sales' vs. 'Predicted Sales' to visually assess the model's performance in tracking demand fluctuations.