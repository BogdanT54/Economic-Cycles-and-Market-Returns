# **📊 Economic Cycles and Market Returns**

Bachelor’s Thesis – Bucharest University of Economic Studies

Major: Statistics and Economic Forecasting

Author: Bogdan-Mihai Tofan


## **📌 Overview**

This thesis examines the interaction between global economic cycles and the returns of key financial assets. The study is divided into two main parts:

Fundamental Analysis – using macroeconomic indicators to identify economic cycle phases.

Technical Analysis – using econometric and statistical models to assess asset performance under different regimes.



### **🎯 Objectives**

- Detect phases of the global economic cycle (expansion, peak, recession, recovery).
- Analyze macroeconomic signals from key indicators (GDP, interest rates, inflation, unemployment, PMI, VIX, M3).
- Evaluate the performance of five major assets: Bitcoin, Gold, Brent Crude Oil, S&P 500, ROTX.
- Apply financial time series analysis models (ARIMA, GARCH, MS-GARCH) to capture volatility regimes and correlations.
- Develop an investment strategy framework aligned with economic cycles.

### **📂 Data Sources**

Macroeconomic indicators:
World Bank, Eurostat, Federal Reserve, BNR

Financial assets:
Bitcoin: CoinMarketCap
Gold, Oil, S&P 500: Yahoo Finance, Investing.com
ROTX: Bucharest Stock Exchange

### **🛠 Methodology:**

Fundamental Analysis – Macroeconomic Indicators
Indicators analyzed: GDP, interest rates (short & long term), inflation (GDP deflator), unemployment rate, PMI, VIX, monetary aggregate M3, recession probabilities (Markov Switching, Sahm Rule).
Statistical tests: Pearson correlations, Granger causality to identify predictive relationships.

Technical Analysis – Financial Assets
Assets analyzed: Bitcoin, Gold, Brent Crude Oil, S&P 500, ROTX.
Data processing: price cleaning, stationarity tests (ADF, KPSS, PP), transformation to log returns.

Models applied:
ARIMA – capturing autoregressive and moving average components.
GARCH / EGARCH – modeling conditional volatility.
MS-GARCH – detecting volatility regimes (low, medium, high) tied to economic phases.

Visualization: Python (Matplotlib, Seaborn), R

### **📊 Key Results**

Fundamental analysis: Macro indicators provided clear signals for cycle phase transitions; strong correlation between global monetary expansion (M3) and real GDP growth.

Technical analysis:
- S&P 500 and ROTX are pro-cyclical, highly sensitive to global liquidity.
- Gold acts as a counter-cyclical safe haven during recessions and crises.
- Bitcoin exhibits extreme volatility with regime shifts linked to liquidity and sentiment shocks.
- Oil prices follow pro-cyclical patterns but are highly exposed to geopolitical shocks.

### **📈 Conclusions**

The integrated fundamental–technical framework shows that cycle-aware investment strategies can significantly improve risk-adjusted returns. Monitoring macroeconomic indicators alongside volatility regimes of financial assets supports timely portfolio adjustments.

### **📜 Keywords**

Economic cycles, Fundamental analysis, Technical analysis, ARIMA, GARCH, MS-GARCH, Macro indicators, Bitcoin, Gold, Oil, S&P 500, ROTX
