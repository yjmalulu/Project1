# 1. Install packages

# 2. Set up the Global Parameters

```python
# Fetch full stocks information from csv, which is downloaded from https://www.nasdaq.com/market-activity/stocks/screener
```

```python
# Check the data
```

```python
# There is only 1 NaN in the Symbol column
```

```python
# Filter out stocks as Market Cap greater than 1 billion, and Volumn greater than 1 million
```

```python
# Check the filtered data again
```

```python
# Get tickers from the DataFrame, and make sure all the data type are string
# for hourly data, yfinance policy restricts the time frame within 730 days
```

# 3. Data Exploration

## 3.1 Data Collection and Reframe

```python
# Fetch stocks historical daily data from yfinance
```

```python
# Fetch Bitcoin historical daily data from yfinance
```

```python
# Check stocks data
```

```python
#Check if there is NULL in the data
```

```python
# Drop the non-useful information and check again
```

```python
#Extract only the "Close" price data
```

```python
# When fetching the data from yfinance, there is a hint warning some tickers are not loaded, so drop them all.
```

```python
# If dropna directly, will lose many data, that means some columns still have NaN 
```

```python
# Fill all the NaN
```

```python
# Check again
```

```python
# Get the BTC close price data
```

```python
# Combine stocks and BTC close price into one DataFrame
```

## 3.2 Correlation within all the assets

### 3.2.1 Regular Correlation Analysis

```python
# Calculate daily returns for each asset, using log method
```

```python
# Show daily returns plot
```

```python
# Calculate the correlation matrix
# Display the correlation matrix
```

```python
# Filter out the correlation greater than 0.4
```

```python
# Create a heatmap for the correlation matrix
```

### 3.2.2 Shift Correlation Analysis

```python
# Shift 2 days for stocks daily return to see if the correlation with BTC will increase
```

```python
# Extract BTC daily return
```

```python
# Combine the shifted stocks daily return with BTC daily return, and calculate its correlation
```

```python
# Check if there is difference for the correlation
# if the correlation after shift is greater than the original, there is a chance BTC would be a leading indicator
```

```python
# The percent change of correlation
```

```python
# Plot the changes of correlation
```

## 3.3 Changes of Correlation over time

```python
    # Generate a correlation matrix between tickers
    # Delete Ticker Index, keep Date Index only
    # Drop and rename columns
```

```python
# Show the correlation between AAPL and BTC over time
```

```python
# Plot the correlation over time
```

## 3.4 Sharpe Ratio of Assets

```python
#Set the annual interest rate
# Construct the portfolio assets
#Calculate the annual volavility of tickers
#Calculate the Sharpe Ratio of tickers
```

```python
#Show the plot of Sharpe Ratio
```

## 3.5 Betas of The Assets Compared With BTC

```python
# Calculate covariance of a single portfolio
# Calculate variance of BTC
# Computing beta
```

```python
# Plot the beta
```

# 4. Finding the efficient frontier using Monte Carlo simulations

## 4.1 Monte Carlo Simulation 

```python
#Set up the Monte Carlo Model parameters
```

```python
#Calculate the portfolio matrixs
```

```python
#Transform to DataFrame
```

## 4.2 Monte Carlo Chart

```python
# Create Tickers DataFrame for Monte Carlo Chart
```

```python
# Tickers Scatter Chart
```

```python
# Simulation Portfolio Scatter Chart
```

```python
# Find out the points on the efficient frontier curve
```

```python
# Plot the efficient frontier curve
```

```python
# Combine the charts
```

## 4.3 Show the highest Sharpe Ratio Portfolio

```python
#Extract the max_sharpe_ratio
```

```python
# Show what is the optimized portfolio
```

```python
# Show Pie Chart for the optimized portfolio
# Unpack the zipped data into separate lists
# Create a pie chart
```

# 5. Comparison with Portfolio and BTC

```python
# Create a optimized portfolio from the result of Monte Carlo Simulation
```

```python
# Plot the cumulative return of portfolio
```

```python
# Calculate BTC cumulative return using log method
```

```python
# Plot the cumulative return of BTC
```

```python
# Combined the plots to show comparison with portfolio and BTC
```

# 6. Backtesing Trading Strategy

## 6.1 Trading strategy 1 rules:
* When portfolio price is above its SMA 20 moving average curve, long the position
* When portfolio price is lower its SMA 20 moving average curve, close the position

```python
# Get the portfolio's close price
```

```python
# Create the SMA 20 curve data
```

```python
# Create trading signal as position
```

```python
# Show how many times the portfolio trades over time
```

```python
# Show the comparison with portfolio and SMA 20 curve
```

```python
# Calculate the strategy return
```

```python
# Calculate the cumulative return of the strategy
```

```python
# Plot the cumulative return of strategy
```

```python
#Combine the plots of portfolio, BTC and strategy return
```

## 6.2 Trading strategy rules: (BTC is the leading indicator)
* When BTC price is above its SMA 20 moving average curve, long the position
* When BTC price is lower its SMA 20 moving average curve, close the position

```python
# Create the BTC SMA 20 curve data
```

```python
# Create trading signal as position
```

```python
# Show how many times the portfolio trades over time
```

```python
# Calculate the strategy return
```

```python
# Calculate the cumulative return of the strategy
```

```python
# Plot the cumulative return of strategy
```

```python
#Combine the plots of portfolio, BTC and strategys return
```

