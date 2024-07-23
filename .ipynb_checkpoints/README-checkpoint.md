# Mercado Trends Forecasting with Prophet

## Overview

This project involves forecasting trends in Mercado data using the Prophet model. The dataset includes search trends and stock price data, with the goal of predicting future trends based on historical data.

## Files

- `mercado_prophet.ipynb`: Jupyter Notebook containing data preparation, Prophet model fitting, and forecasting steps.

## Dependencies

- `pandas`: For data manipulation and analysis.
- `matplotlib`: For visualization.
- `prophet`: For time-series forecasting.
- `numpy`: For numerical operations.

## Data

### DataFrames

1. **`df_mercado_trends`**:
   - Contains search trends data with a datetime index.
   - Columns: `Search Trends`

2. **`df_mercado_stock`**:
   - Contains stock price data with a datetime index.
   - Columns: `close`

3. **`mercado_stock_trends_df`**:
   - Combined DataFrame of stock and search trends data.
   - Columns: `close`, `Search Trends`

## Steps

### 1. Data Preparation

1. **Load Data**: Import the necessary datasets.
2. **Combine DataFrames**: Concatenate `df_mercado_stock` and `df_mercado_trends` by columns.
3. **Clean Data**: Remove rows with missing data, if any.

### 2. Prophet Model

1. **Prepare Data for Prophet**:
   - Reset the index and rename columns to `ds` (datetime) and `y` (values).
   - Drop NaN values.

2. **Initialize Prophet Model**:
   - Create an instance of the Prophet model.

3. **Fit the Model**:
   - Train the model using the prepared DataFrame.

4. **Forecast Future Data**:
   - Create a future DataFrame extending 2000 hours.
   - Make predictions using the fitted model.

5. **Visualize Results**:
   - Plot forecast results including trend and uncertainty intervals.
   - Use `plot_components()` to visualize the trend, seasonality, and other components.

## Code Examples

### Plotting Forecast

```python
import matplotlib.pyplot as plt

# Plot the Prophet predictions
fig = prophet_model.plot(forecast_mercado_trends)

# Customize the plot
plt.title('Prophet Predictions for Mercado Trends')
plt.xlabel('Date')
plt.ylabel('Search Trends')
plt.show()
