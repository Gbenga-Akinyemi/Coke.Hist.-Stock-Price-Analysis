# Coca-Cola: Historical Stock Prices(1961-2023)
## Project Overview
This is focused on analyzing long-year( 1961-2023) stock price data for Coca-Cola, comparing it with the general stock market price for the same period. 
The proxy for the general stock market price is represented by the S&P 500, that is, the stock prices of the best and biggest 500 companies in the US. The major technique of analysis applied is linear regression to gain insight into Coca-Cola stock prices could explain the rise in the  general stock market performance, or vice versa. 

## Data  Preparation and Cleaning 
The original data sourced from [see here](https://www.kaggle.com/datasets/henryshan/coca-cola-stock-price) only contained Coca-Cola  stock prices historical data. 
This was discovered after preliminary viewing of the data using the head and tail function in Python. There was a need to have  S & P 500 data arranged horizontally. 
I resorted to using Python libraries to clean, arrange and download Coca-Cola historical stock prices (1961-2023) and S&P 500 historical stock prices (1961-2023), side by side.

  - Data was arranged in columns to have fields such as opening stock prices, adj closing stock prices and  closing stock prices.
  - Python libraries were used to arrange the data and pulled them from sources such as Yahoo Finance
     
- Python codes for pulling and arranging data from source   
import yfinance as yf
import pandas as pd

#### Define the ticker symbols for S&P 500 and Coca-Cola
sp500_ticker = '^GSPC'
coca_cola_ticker = 'KO'

#### Define the date range (from 1962-01-01 to the present date)
start_date = '1962-01-01'
end_date = pd.to_datetime('today').strftime('%Y-%m-%d')

#### Download historical data from Yahoo Finance
sp500_data = yf.download(sp500_ticker, start=start_date, end=end_date)
coca_cola_data = yf.download(coca_cola_ticker, start=start_date, end=end_date)

#### Display the first few rows of the data
print("S&P 500 Data:")
print(sp500_data.head())

print("\nCoca-Cola Data:")
print(coca_cola_data.head())

## Preliminary  and Exploratory Analysis 
The analysis is essentially  a linear regresion of a long range of dataset. The  important to do is to first check for correlational analysis. Thus was carried out to check pattern of association. 

