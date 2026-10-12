# AAPL Stock Price Forecasting with PyTorch LSTM

## Overview

This project uses a Long Short-Term Memory (LSTM) neural network implemented in PyTorch to forecast Apple's (AAPL) next-day closing stock price using historical closing-price data.

Historical data is retrieved using `yfinance`. The model uses a rolling window of the previous 60 trading days to predict the following trading day's closing price.

## Methods

- **Data source:** Yahoo Finance through `yfinance`
- **Input feature:** Historical AAPL closing prices
- **Preprocessing:** Min-max scaling and chronological train-test splitting
- **Sequence length:** 60 trading days
- **Model:** Two-layer LSTM with dropout and a linear output layer
- **Framework:** PyTorch
- **Evaluation:** Root Mean Squared Error (RMSE)

## Results

The submitted model achieved a scaled test RMSE of 0.0284. This value is measured on the normalized price scale, not in dollars.

The notebook includes visualizations of historical prices, training loss, and predicted versus actual closing prices.

## Saved Model

The trained LSTM model weights are saved in `model_proj2.pth`. This file contains the model's learned parameters and allows the trained model to be reloaded without repeating the training process.

The saved weights must be loaded into the same LSTM architecture used during training. The input data must also undergo the same preprocessing and scaling steps before generating predictions.

**Note:** The `.pth` file contains model weights only. It does not include the training dataset, model architecture, or preprocessing objects.

## Limitations

This project uses historical closing prices as its only input feature. It does not incorporate trading volume, financial statements, market sentiment, or other external variables.

Stock prices are affected by unpredictable events and broader market conditions. The model is an educational forecasting exercise, not a trading strategy or investment recommendation. Performance on historical data does not guarantee future results.

## Setup

1. Clone this repository.
2. Install the dependencies listed in `requirements.txt`.
3. Open `aapl_lstm_forecasting.ipynb` in Jupyter or VS Code.
4. Run the notebook cells in order.

The notebook downloads historical data when executed, so results may vary as new market data becomes available.

## Technologies

Python, PyTorch, pandas, NumPy, scikit-learn, Matplotlib, and yfinance.