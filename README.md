# Financial Time Series Forecasting: Comparing Statistical and Machine Learning Models

## Overview

This project focuses on forecasting Bitcoin's next-day closing price using historical financial time-series data.

The project compares a simple baseline, statistical time-series modeling, and machine learning models to examine their forecasting performance.

The analysis is implemented in Python using daily Bitcoin market data derived from historical minute-level observations.

## Objective

The main objective is to develop and compare different approaches for next-day Bitcoin price forecasting.

The project includes:

* Data preprocessing and cleaning
* Exploratory data analysis
* Financial time-series feature engineering
* Statistical forecasting
* Machine learning models
* Model evaluation using forecasting metrics

## Dataset

The dataset contains historical Bitcoin market data with:

* Open price
* High price
* Low price
* Close price
* Trading volume
* Timestamp

The original data is provided at the minute level and is aggregated into daily observations for the analysis.

The raw dataset is not included in this repository.

## Methodology

### 1. Data Preprocessing

The data preprocessing steps include:

* Loading the historical Bitcoin dataset
* Checking the dataset structure and missing values
* Converting Unix timestamps to datetime format
* Sorting observations chronologically
* Setting the timestamp as the index
* Aggregating minute-level observations into daily OHLCV data
* Removing incomplete observations

### 2. Exploratory Data Analysis

The project examines Bitcoin's:

* Closing price
* Trading volume
* Daily returns
* Rolling volatility

Daily returns are calculated using percentage changes in the closing price.

A 30-day rolling standard deviation is used as a measure of volatility.

### 3. Feature Engineering

The following features are created for forecasting:

* Current closing price
* Trading volume
* Daily return
* 30-day volatility
* 1-day lagged closing price
* 7-day lagged closing price
* 7-day moving average
* 30-day moving average
* Percentage change in trading volume

The prediction target is the following day's Bitcoin closing price.

### 4. Forecasting Models

The following approaches are implemented:

**Baseline**

A previous-day closing price is used as a simple benchmark for next-day forecasting.

**Linear Regression**

A linear regression model is used to establish a basic machine learning forecasting model.

**Random Forest**

A Random Forest Regressor is used to capture nonlinear relationships between the engineered features and the target variable.

**XGBoost**

An XGBoost regression model is used as a gradient-boosting approach for nonlinear prediction.

**ARIMA**

An ARIMA model is applied to the Bitcoin closing-price time series after examining stationarity using the Augmented Dickey-Fuller (ADF) test.

**GARCH**

A GARCH(1,1) model is used to examine and forecast the volatility of Bitcoin returns.

## Model Evaluation

The forecasting models are evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Percentage Error (MAPE)

The train-test split follows the chronological order of the time series, with approximately 80% of the observations used for training and 20% for testing.

This time-based split avoids randomly mixing past and future observations.

## Technologies

The project uses:

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* XGBoost
* Statsmodels
* ARCH

## Project Structure

```text
bitcoin-price-forecasting/
│
├── README.md
│
└── bitcoin_forecasting.ipynb
```

## Limitations

This project is primarily a forecasting and modeling exercise.

The models are evaluated using historical Bitcoin data and should not be interpreted as a trading strategy or financial advice.

The current implementation focuses on a limited set of engineered features and does not include external market, macroeconomic, sentiment, or blockchain-specific variables.

## Future Work

Potential extensions include:

* Hyperparameter tuning
* Additional time-series models
* More advanced machine learning models
* Walk-forward validation
* Feature importance analysis
* Ensemble forecasting
* Additional predictive features

## Author

**Paria Modares**

M.Sc. Financial Engineering  
B.Sc. Industrial Engineering

Research interests: Operations Research, Supply Chain Analytics, Machine Learning, Time Series Analysis, Optimization, and Data-Driven Decision Making.
