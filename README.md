# Air-pollution-using-Linear-regression

## Project Overview
This project focuses on forecasting PM2.5 air pollution levels using **Linear Regression**.  
Predictions are performed for three different forecasting horizons:

- **1 Hour Ahead**
- **24 Hours Ahead**
- **1 Week Ahead**

The objective is to evaluate how Linear Regression performs for short-term and long-term air quality prediction.


## Dataset Description
- File type: `data.csv`
- Target variable: `PM2.5`
- Input features:
  - PM2.5
  - Dew Point (DEWP)
  - Temperature (TEMP)
  - Pressure (PRES)
  - Wind Speed (Iws)
  - Snow (Is)
  - Rain (Ir)

Missing values are handled using forward-fill and backward-fill techniques.


## Methodology

### Data Preprocessing
- Renaming column `pm2.5` to `pm25`
- Handling missing values
- Selecting relevant meteorological features
- Normalizing data using Min-Max scaling

### Model
- Algorithm: **Multiple Linear Regression**
- Library used: **scikit-learn**


## Forecasting Strategy

### 1-Hour Prediction
- One-step ahead prediction
- Uses actual historical values
- Provides stable and accurate results

### 24-Hour Prediction
- Recursive (rolling) forecasting
- Each predicted value is fed back as input
- Error gradually accumulates

### 1-Week Prediction (168 Hours)
- Long-horizon recursive forecasting
- Demonstrates the limitation of Linear Regression
- Significant deviation observed in long-term prediction



## Evaluation Metrics
- Root Mean Square Error (RMSE)
- Visual comparison using Actual vs Predicted plots



## Results Summary

| Forecast Horizon | Observation |
|----------------|-------------|
| 1 Hour | High accuracy |
| 24 Hours | Moderate deviation |
| 1 Week | Large error accumulation |

Linear Regression performs well for short-term forecasting but is not suitable for long-term PM2.5 prediction due to its linear nature.



## Output
The program generates:
- Actual vs Predicted PM2.5 graphs for:
  - 1 hour
  - 24 hours
  - 1 week
- RMSE values for each forecasting horizon

All output plots are stored in the project output directory.



## Conclusion
This project establishes Linear Regression as a baseline model for PM2.5 prediction.  
While effective for short-term forecasting, its performance degrades for long-term prediction, highlighting the need for advanced time-series models such as LSTM.

