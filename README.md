# Predict_Taxi_Trip_Duration

## Problem Statement
The goal of this project is to predict the **duration of taxi trips** based on various features provided in the dataset. Using data from individual taxi trips, we aim to develop a model that accurately estimates trip durations.

## Dataset Description
The dataset for this project is derived from the **2016 NYC Yellow Cab trip records**, made available in **BigQuery on Google Cloud Platform**. Originally published by the **NYC Taxi and Limousine Commission (TLC)**, the data has been sampled and cleaned for use in this project. The task is to predict the duration of each trip in the test set based on various trip-related attributes.

The training dataset, **NYC Taxi Data.csv**, consists of **1,458,644** trip records. These records include information such as pickup and dropoff times, locations, and other relevant trip features.

## Data Fields (Columns in Dataset)
The dataset contains detailed information about individual taxi trips. Below are the descriptions of each feature:

| **Column Name**       | **Description**                                                                                                                                   |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                  | Unique identifier for each trip.                                                                                                                 |
| `vendor_id`           | ID of the taxi vendor (1 or 2).                                                                                                                  |
| `pickup_datetime`      | The timestamp when the taxi trip started.                                                                                                        |
| `dropoff_datetime`     | The timestamp when the taxi trip ended.                                                                                                          |
| `passenger_count`      | Number of passengers in the taxi.                                                                                                                |
| `pickup_longitude`     | The longitude of the pickup location.                                                                                                            |
| `pickup_latitude`      | The latitude of the pickup location.                                                                                                             |
| `dropoff_longitude`    | The longitude of the dropoff location.                                                                                                           |
| `dropoff_latitude`     | The latitude of the dropoff location.                                                                                                            |
| `store_and_fwd_flag`   | Indicates whether the trip record was stored and forwarded because the vehicle did not have a connection to the server (`Y` for Yes, `N` for No). |
| `trip_duration`        | The duration of the trip in seconds (this is the target variable to be predicted).                                                               |

## Objective
The main objective is to build a predictive model using the features provided in the dataset to forecast the trip duration (in seconds or minutes) for each taxi trip.

## Getting Started
### Prerequisites
- Python 3.x
- Required libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `haversine`

## Major Steps in the Project

1. **Import Data and Libraries**: Loaded the necessary libraries and the dataset into the environment for analysis and modeling.
   
2. **Exploratory Data Analysis (EDA)**: Conducted EDA to understand the data distribution, identify patterns, and gain insights from the variables, including visualizations for better interpretation.
   
3. **Data Cleaning and Feature Engineering**: Handled missing values, removed outliers, and created new features (such as extracting day of the week, hour of the day, and calculating distances) to improve model performance.
   
4. **Data Preparation**: Prepared the data for model training, including encoding categorical variables, normalizing/standardizing features, and splitting the data into training and test sets.
   
5. **Model Selection**: Tested different machine learning algorithms such as Linear Regression, Decision Tree Regressor, XG Boost Regressor, and Hist Gradient Boosting Regressor to identify the best-performing model.
   
6. **Hyperparameter Tuning**: Specifically tuned the **HistGradientBoostingRegressor** for better results, fine-tuning its hyperparameters to improve predictive accuracy and overall performance.
   
**Conclusions**: Summarized the model performance, key insights.
Distance calculated using the haversine function plays an important role in predicting the trip durations.

Rest of the features showed moderate to very little linear correlation with the dependent variable.

Before HyperParameter Tuning,The XG Boost Regressor appears to be the best model based on both the highest Test R² Score and the lowest Test RMSE Score.

The untuned model of Hist Gradient Boosting Regressor was able to explain 68% of the variance on the test set, while the tuned model explained 74% of variance on the test set which is a good improvement.

The least RMSE on test set by the Hist Gradient Boosting Regressor was 3.367436 which is comparatively lower when compared with rest of the models.

