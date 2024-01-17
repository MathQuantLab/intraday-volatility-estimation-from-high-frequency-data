# Intraday Volatility Estimation from High-Frequency Data 📉📈

**Authors:** Sarahnour Ghaith & Thomas Roiseux  
**Academic Year:** 2023-2024

## Overview 📚

This repository contains the code and documentation for a project focused on intraday volatility estimation from high-frequency data. Python is used for computational tasks, with detailed calculations and model simulations provided in the attached Jupyter Notebook file.

## 1. Introduction 🚀

The project aims to estimate daily volatility from high-frequency time series data, considering the impact of microstructure noise. The analysis uses tick data from iShares S&P 500 Value ETF (IVE) with the following objectives:

1. Estimate and visually represent realized volatility at observation frequencies from 30 seconds to 15 minutes.
2. Compare intraday estimates with a long-term estimation based on one month of daily data.
3. Assess the size of microstructure noise through methods such as autocorrelation between returns at different scales.

The data is sourced from [KIBOT - Free historical intraday data](http://www.kibot.com/free_historical_data.aspx) for iShares S&P (IVE).

## 2. Data Collection 📊

### Chosen Dataset
- **Dataset:** iShares S&P 500 Value ETF (IVE) tick data
- **Data Structure:** Date, Time, Price, Bid, Ask, Size

The dataset provides transaction-specific details, including timestamps and prices, facilitating a detailed analysis of high-frequency market dynamics for large-cap U.S. value stocks.

## 3. Pre-processing 🧹

### 3.1 Data Cleaning and Filtering
Outlier price values (below $10) were removed after loading the data.

### 3.2 Organizing Data into Time Series Format
The data is organized into a time series format, enabling the visualization of all timestamps and associated prices.

## 4. Intraday Volatility Estimation 📊

### 4.1 Introduction to Realized Volatility
Realized volatility is computed using past index values with the formula:

$$\mathit{RV} = \sum_{i=1}^{n} (X_{t_i+1} - X_{t_i})^2$$

### 4.2 Estimation Method: Rolling Window Approach
Realized volatility is computed using a rolling window approach with various time intervals.

### 4.3 Visual Representation
Realized volatility with variable time intervals is illustrated.

## 5. Long-Range Volatility Estimation 📈

### 5.1 Estimating Volatility Based on 1 Month of Daily Data
Volatility is computed using daily data for the same month, allowing for a comparison with intraday volatility estimates.

### 5.2 Comparing Intraday and Long-Range Volatility
Long-range volatility during the same month is compared to intraday volatility trends.

## 6. Microstructure Noise Analysis 🔍

### 6.1 Introduction to Microstructure Noise
Microstructure noise, resulting from the ask & bid mechanism, interferes with prices and modifies predictions made by regular models.

### 6.2 Methodology for Estimating Noise Size
The estimator $\eta$ of microstructure noise size is computed using a large sample size.

### 6.3 Computation of the Estimator
Daily microstructure noise is illustrated based on computations from January 1, 2022, to today.

### 6.4 Autocorrelation
Microstructure noise is further analyzed using autocorrelation on log-prices, revealing its impact on prices.

## 7. Estimated Daily Volatility 📆

Estimated daily volatility over the last year is presented.

## 8. Conclusion 🎓

The analysis of realized volatility offers advantages such as simplicity and the use of intra-daily log returns. Challenges include the impact of market microstructure noise and the influence of overnight returns. Industry and academic solutions developed over the past two decades aim to refine volatility estimation techniques for a more accurate understanding of financial market dynamics.

## References 📚

1. Cristina Mabel Scherrer, Gustavo Fruet, and Dias Marcelo Fernandes. Price discovery and market microstructure noise. SSRN.
2. Ruey Tsay. Analysis of financial time series. Wiley series in probability and statistics. Wiley, 2005.
