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
The analysis is essentially  a linear regression of a long range of datasets. The  important thing is to first check for correlational analysis. Thus was carried out to check the pattern of association. 

- correlation where Coca-Cola stock price is the x(independent variable)
  
![correlation_plot](https://github.com/Gbenga-Akinyemi/Coke.Hist.-Stock-Price-Analysis/assets/102978818/1fd61126-f258-4768-8211-6bcd3c65e4dd) 

- Correction where Coca-Cola stock price is the y(dependent variable)
  
  
![correlation_visualization cc as independent  png](https://github.com/Gbenga-Akinyemi/Coke.Hist.-Stock-Price-Analysis/assets/102978818/5540f41e-7ef2-46fa-bdc8-78c20ce6504a) 


In both analyses, Coca-Cola stock correlates with SP500 at 0.94 positive. This  shows a strong  positive significant relationship. 

- Correlation with regression line further clearly depicts the direction of the association. 


![regression_plot](https://github.com/Gbenga-Akinyemi/Coke.Hist.-Stock-Price-Analysis/assets/102978818/241796b2-b49f-434a-8bc8-1da0bdd44c69) 

## Regression Analysis 

Analysis was done by switching  the role( switching the variables) at a time  when Coca-Cola stock price was treated as the X( the independent variable ) while SP 500 was taken as the dependent variable. In the second round of analysis, the roles were reversed. However, the result of the analysis proved to be the same.

![sp500_results](https://github.com/Gbenga-Akinyemi/Coke.Hist.-Stock-Price-Analysis/assets/102978818/cc56228c-cbdb-4066-b8ad-2c5d13d83eeb) 


![coca_cola_results](https://github.com/Gbenga-Akinyemi/Coke.Hist.-Stock-Price-Analysis/assets/102978818/4d1258d9-3751-4823-b834-a4fdfc1683f1)


The variables were switched to enrich the quality of the analysis. Theoretically, it might be difficult to emphatically establish which variable predicts the other among Coca-Cola  and SP500 which proxied the general market stock prices. However, common-sensically,  it could be safe to conclude that the general stock market might have some measure of impact over Coca- Coca-Cola stock prices.

- Summary of regression analysis:

#### Regression Results - Coca-Cola Closing Prices:

- **R-squared:** 0.887 (implies 88.7% explanatory power)
- **F-statistic:** Highly significant (p < 0.05)
- **Intercept:** 2.6242 (Estimated Coca-Cola closing price when S&P 500 is zero)
- **SP500_Close Coefficient:** 0.0161 (On average, each one-unit increase in S&P 500 corresponds to a 0.0161 increase in Coca-Cola closing prices)

#### Regression Results - S&P 500 Closing Prices:

- **R-squared:** 0.887 (implies 88.7% explanatory power)
- **F-statistic:** Highly significant (p < 0.05)
- **Intercept:** -40.5312 (Estimated S&P 500 closing price when Coca-Cola is zero)
- **CocaCola_Close Coefficient:** 55.2114 (On average, each one-unit increase in Coca-Cola corresponds to a 55.2114 increase in S&P 500 closing prices)

####  Overall Interpretation:

Both models exhibit high explanatory power and statistical significance over each other. The positive coefficients indicate a positive relationship. Please remember, that this has already been pointed to by the preliminary analysis, the correlation. As the S&P 500 increases, Coca-Cola closing prices tend to increase, and vice versa. This suggests potential interdependence between Coca-Cola and the broader market. 

## Conclusion 
Thus, further research is needed to understand the foundational connection between  Coca-Cola Stock prices and SP500. 


## References 
1. Coca-Cola Historical Stock prices (1961 to date) [Download from here](https://www.kaggle.com/datasets/henryshan/coca-cola-stock-price)
2. Yahoo Finance/ Python yfinance library 







