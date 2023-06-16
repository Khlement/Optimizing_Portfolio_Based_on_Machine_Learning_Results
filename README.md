# Optimizing Portfolio Based on Machine Learning Results
Machine learning code to optimize an investment portfolio. It uses historical financial data to train a machine learning model(a Long Short-Term Memory (LSTM) model) to predict the future returns of various stocks. Based on these predictions, the code then calculates an optimized portfolio allocation that maximizes returns while minimizing risk. The purpose of this code is to provide investors with a tool to make data-driven decisions about their investments and improve the overall performance of their portfolio.

## Model development
### Data
**Top 30 U.S. companies by market capitalization** are used. 

Access csv files containing the data for all the companies from *stock_price_data* folder

### Task
The main purpose is to maximize overall return by creating an investment portfolio from stocks. 
An investment portfolio of several stocks is created by making stock price predictions using an **LSTM Univariate Time-Series Prediction** model. Daily returns are then are computed from the predicted stock prices and used to get weights that maximize overall return. This is done using **SLSQP (Sequential Least SQuares Programming)** optimization.

To create the **features** of the LSTM model, a time step of **100 days** is used. This means that if we consider today's Adj Close price as the **response,** the features will be the Adj Close prices of the past 100 days.

LSTM model **parameters:**

- `input_size=1`
- `hidden_size=1`
- `num_layers=1`
- `batch_first=True`
- `num_classes=1`
- `learning_rate=0.001`
- `optimizer=Adam`
- - `loss_function=MSELoss()`
- `num_epochs=10000`
***GPU** is leveraged.*

<p align="center">
  <img src="https://user-images.githubusercontent.com/21691211/155658959-cfd8f6cf-2baa-4a6a-afa8-274e7eddb3fd.png">
</p>

## <a href="https://github.com/georgemuriithi/investment-portfolio-optim/blob/main/Investment-Portfolio-Optimization.ipynb">Solution Approach</a>
<a href="https://colab.research.google.com/drive/1Rd7xhUgp3OQO5u-bGqIT4cb29zJvWeXG?usp=sharing">
    <img alt="Open In Colab" src="https://colab.research.google.com/assets/colab-badge.svg">
</a>







