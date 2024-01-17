# Intraday Volatility Estimation from High-Frequency Data 📈📊

**Authors:** Sarahnour Ghaith & Thomas Roiseux  
**Academic Year:** 2023-2024

## Overview 📚

This repository contains the code and documentation for a project focused on intraday volatility estimation from high-frequency data. The project utilizes Python for computational tasks, with detailed calculations and model simulations provided in the attached Jupyter Notebook file.

## 1. Introduction 

The primary objective of this project is to estimate daily volatility from high-frequency time series data while considering the impact of microstructure noise. The analysis is performed on tick data from iShares S&P 500 Value ETF (IVE). The key goals include:

1. Estimating and visually representing realized volatility at observation frequencies ranging from 30 seconds to 15 minutes.
2. Comparing these intraday estimates with a long-term estimation based on one month of daily data.
3. Assessing the size of microstructure noise through methods such as autocorrelation between returns at different scales.

The data for this analysis is sourced from KIBOT, offering free historical intraday data, specifically the tick data for iShares S&P (IVE), allowing for a comprehensive exploration of intraday volatility evolution over the past year.

## 2. Data Collection 

### Chosen Dataset
- **Dataset:** iShares S&P 500 Value ETF (IVE) tick data
- **Source:** [KIBOT - Free historical intraday data](http://www.kibot.com/free_historical_data.aspx)
- **Data Structure:** Date, Time, Price, Bid, Ask, Size

The dataset provides transaction-specific details, including timestamps and prices, facilitating a detailed analysis of high-frequency market dynamics for large-cap U.S. value stocks.

## 3. Pre-processing

### 3.1 Data Cleaning and Filtering
After loading the data, outlier price values (below $10) were removed, considering the large dataset's size.

### 3.2 Organizing Data into Time Series Format
The data is organized into a time series format, enabling the visualization of all timestamps and associated prices. Figure 1 illustrates all prices since September 30, 2009.

![Figure 1](path/to/figure1.png)

## 4. Intraday Volatility Estimation

### 4.1 Introduction to Realized Volatility
Realized volatility is computed using past index values, as defined by the formula:

\[RV = \sum_{i=1}^{n} (X_{t_i+1} - X_{t_i})^2\]

### 4.2 Estimation Method: Rolling Window Approach
The realized volatility is computed using a rolling window approach. Various time intervals are selected to parse data, and the realized volatility is calculated with the remaining data.

### 4.3 Visual Representation
Figure 2 illustrates realized volatility with variable time intervals.

![Figure 2](path/to/figure2.png)

## 5. Long-Range Volatility Estimation

### 5.1 Estimating Volatility Based on 1 Month of Daily Data
Volatility is computed using daily data for the same month, allowing for a comparison with intraday volatility estimates.

### 5.2 Comparing Intraday and Long-Range Volatility
Figure 3 shows long-range volatility during the same month, highlighting differences from intraday volatility trends.

![Figure 3](path/to/figure3.png)

## 6. Microstructure Noise Analysis

### 6.1 Introduction to Microstructure Noise
Microstructure noise, resulting from the ask & bid mechanism, interferes with prices and modifies predictions made by regular models like Brownian motion.

### 6.2 Methodology for Estimating Noise Size
The estimator \(\eta\) of microstructure noise size is computed using a large sample size, demonstrating its importance and impact.

### 6.3 Computation of the Estimator
Figure 5 illustrates daily microstructure noise based on computations from January 1, 2022, to today.

![Figure 5](path/to/figure5.png)

### 6.4 Autocorrelation
Microstructure noise is further analyzed using autocorrelation on log-prices, revealing its impact on prices.

![Figure 6](path/to/figure6.png)

## 7. Estimated Daily Volatility

Figure 7 presents estimated daily volatility over the last year, with the red line representing daily volatility and the green line indicating average volatility.

![Figure 7](path/to/figure7.png)

## 8. Conclusion

In conclusion, the analysis of realized volatility offers advantages such as simplicity and the use of intra-daily log returns. Challenges include the impact of market microstructure noise and the influence of overnight returns. The project acknowledges industry and academic solutions developed over the past two decades to refine volatility estimation techniques for a more accurate understanding of financial market dynamics.

## References

1. Cristina Mabel Scherrer, Gustavo Fruet, and Dias Marcelo Fernandes. Price discovery and market microstructure noise. SSRN.
2. Ruey Tsay. Analysis of financial time series. Wiley series in probability and statistics. Wiley, 2005.
