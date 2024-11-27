# Pet Inflation Data Analysis with Prophet

## Overview
This project performs a comprehensive time series analysis of pet inflation using Facebook's Prophet forecasting model. The analysis includes exploratory data analysis, feature engineering, model tuning, and forecasting.

## Table of Contents
- [Libraries Used](#libraries-used)
- [Data Loading](#data-loading)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature Engineering](#feature-engineering)
- [Prophet Model](#prophet-model)
- [Cross-Validation](#cross-validation)
- [Parameter Tuning](#parameter-tuning)
- [Forecasting](#forecasting)
- [Visualizations](#visualizations)
- [Model Performance](#model-performance)

## Prerequisites
- Python 3.7+
- Libraries: 
  - pandas
  - matplotlib
  - statsmodels
  - scikit-learn
  - prophet
  - plotly (optional)

## Installation
```bash
pip install pandas matplotlib statsmodels scikit-learn prophet plotly
```

## Data Preparation
The dataset contains monthly pet inflation data from 2017 to 2024, with columns:
- `DATE`: Date of observation
- `inflation`: Inflation rate
- `Food`: Pet food price index

## Key Steps in Analysis

### 1. Libraries and Data Loading
```python
import pandas as pd
import matplotlib.pyplot as plt
import statsmodels.api as sm
from prophet import Prophet

# Load data
df = pd.read_csv("pet inflationup to 2024.csv")
```

### 2. Data Preprocessing
- Converted date format
- Renamed columns
- Created time series index
- Added feature lags

### 3. Exploratory Data Analysis
The script includes several visualizations:
- Monthly inflation line plot
- Monthly seasonality plot
- Quarterly seasonality plot
- Autocorrelation Function (ACF)
- Partial Autocorrelation Function (PACF)

### 4. Prophet Model Configuration
Key model parameters:
- Yearly seasonality
- Additive seasonality
- External regressor: Pet food prices

### 5. Model Tuning
Parameters tuned:
- `changepoint_prior_scale`
- `seasonality_prior_scale`
- `seasonality_mode`

### 6. Cross-Validation Metrics
- RMSE: 1.0
- MAPE: 13.89%

## Forecasting
The model forecasts pet inflation for 24 months beyond the existing data, using the last known pet food price as a constant external regressor.

## Visualizations
The script generates:
- Actual vs Forecast plot
- 
- ![image](https://github.com/user-attachments/assets/db728d01-afb5-4605-aefc-a9b862f4e41d)

- Forecast components plot

- ![image](https://github.com/user-attachments/assets/f655a682-b6e8-41bc-ad1b-23527ccf83c9)

- Interactive Plotly visualization

- ![image](https://github.com/user-attachments/assets/78c27071-c901-4e9a-a00c-6038678fa33d)

- ![image](https://github.com/user-attachments/assets/41f1699f-09e0-4fe9-b1e0-39cdac809598)



## Model Performance
- Cross-validation reveals consistent performance across different forecast horizons
- Low Mean Absolute Percentage Error (MAPE)
- Uncertainty intervals provided for forecast

## How to Use
1. Clone the repository
2. Install required libraries
3. Place your CSV file in the project directory
4. Run the Jupyter notebook or Python script

## Limitations
- Uses constant pet food price for future forecasting
- Limited to historical patterns
- Performance may vary with significant market changes

## Future Improvements
- Incorporate more external regressors
- Experiment with advanced time series techniques
- Add more sophisticated feature engineering

