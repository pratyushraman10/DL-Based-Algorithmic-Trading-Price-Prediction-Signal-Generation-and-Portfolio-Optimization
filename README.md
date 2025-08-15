# Deep Learning-Based Algorithmic Trading: Price Prediction, Signal Generation, and Portfolio Optimization

Overview
--------
This project implements an end-to-end algorithmic trading system using LSTM and Transformer models to predict stock prices and simulate trading performance. It fetches historical price data, computes technical indicators, trains deep learning models, and visualizes results to support trading decisions.

Features
--------
- Fetches historical OHLCV data from Yahoo Finance using yfinance
- Computes technical indicators such as EMA, SMA, RSI, and MACD
- Implements LSTM and Transformer models for price prediction
- Constructs input sequences for time series forecasting
- Evaluates predictions against actual prices using MSE/MAE metrics
- Portfolio simulation with normalized growth and daily returns
- Visualizations including historical vs predicted prices, portfolio growth, and daily returns
- Modular design allowing extensions for multi-stock predictions, portfolio optimization, or alternative models

Requirements
------------
- Python 3.8+
- Packages:
  yfinance
  numpy
  pandas
  matplotlib
  seaborn
  scikit-learn
  tensorflow
  ta

Install dependencies: 
pip install yfinance numpy pandas matplotlib seaborn scikit-learn tensorflow ta

How It Works
------------
Data Retrieval
- Downloads historical stock prices for a selected symbol and date range
- Cleans data and ensures all columns are properly formatted

Feature Engineering
- Computes technical indicators and returns for predictive modeling
- Normalizes features using StandardScaler for model input

Model Training
- Defines LSTM or Transformer architecture
- Trains model on historical sequences to predict next-day or multi-step prices
- Supports regression (price prediction) or classification (directional movement)

Prediction & Evaluation
- Generates predicted prices for validation/test set
- Compares predictions with actual prices
- Computes performance metrics (MSE, MAE, accuracy)

Visualization
- Plots historical vs predicted prices
- Shows portfolio growth and normalized returns
- Displays daily returns for performance analysis

Usage
-----
1. Clone this repository and save the Python scripts (e.g., main.py, models.py, utils.py)

2. Install dependencies listed above

3. Configure parameters:

CFG = {
    "ticker": "AAPL",
    "start_date": "2022-01-01",
    "end_date": "2025-01-01",
    "seq_len": 60,
    "pred_horizon": 1,
    "target_mode": "regression"
}

4. Run pipeline:

model, results, metrics = run(CFG)

5. Visualize results:

plot_price_vs_prediction(results)
plot_portfolio_growth(portfolio_values)
plot_daily_returns(portfolio_values)

Possible Extensions
-------------------
- Multi-step forecasting for weekly or monthly returns
- Implement automated buy/sell signals and backtesting
- Optimize portfolios with multiple assets using predicted returns
- Integrate exogenous features such as macroeconomic indicators or news sentiment
- Explore hybrid LSTM-Transformer or attention-based models
- Incorporate risk-adjusted performance metrics (Sharpe ratio, drawdown)

Disclaimer
----------
This project is for educational purposes only. It is not financial advice and should not be used for live trading. Past simulated results do not guarantee future performance.
