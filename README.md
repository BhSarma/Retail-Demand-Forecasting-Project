# Retail Demand Forecasting (Time Series)

Forecasting total daily retail sales with classical time series models in Python.

**Dataset:** [Store Item Demand Forecasting Challenge](https://www.kaggle.com/c/demand-forecasting-kernels-only) (Kaggle) - 5 years of daily sales (2013-2017), 10 stores, 50 items, 913,000 rows.

## Business problem
Retailers need to know how many units they will sell so they can plan inventory and staffing. This project forecasts total daily demand for the next 30 days.

## Approach
1. **EDA** - trend, weekly and yearly seasonality, store and item comparison
2. **Decomposition** - weekly (period 7) and yearly (period 365)
3. **Stationarity** - rolling statistics, ADF test, first-order differencing, ACF / PACF
4. **Models** - Naive, Seasonal Naive, AR(7), MA(7), ARIMA(2,1,2), SARIMA, SARIMAX with Fourier terms (yearly seasonality)
5. **Evaluation** - 90-day hold-out set, MAPE / RMSE / MAE
6. **Validation** - walk-forward validation (4 folds x 30 days) and residual diagnostics (Ljung-Box)
7. **Forecast** - next 30 days with 95% confidence interval

## Results
Fill in after running the notebook (see `outputs/model_comparison.csv`):

| Model | MAPE (%) | RMSE | MAE |
|---|---|---|---|
| ... | ... | ... | ... |

![forecast](outputs/final_forecast.png)

## How to run
```bash
pip install -r requirements.txt
# download train.csv from Kaggle and place it next to the notebook
jupyter notebook Retail_Demand_Forecasting.ipynb
```
Running all cells takes a few minutes (SARIMA models and walk-forward validation are the slow parts). Charts and tables are saved to `outputs/`.

## Tech stack
Python, pandas, NumPy, statsmodels, scikit-learn, matplotlib, seaborn
