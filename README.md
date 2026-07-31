# Economic Cycles and Market Returns

> If you can tell which phase of the economic cycle you are in, can you tell which assets to hold?

Bachelor's thesis at the Bucharest University of Economic Studies, Statistics and Economic Forecasting. Graded 10. It connects two things that are usually studied separately: the macroeconomic signals that identify where the global economy sits in its cycle, and the volatility regimes of the assets you would actually invest in.

![Python](https://img.shields.io/badge/Python-analysis-3776AB?logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-MS--GARCH-276DC3?logo=r&logoColor=white)
![statsmodels](https://img.shields.io/badge/ARIMA%20%7C%20GARCH%20%7C%20EGARCH-4B8BBE)
![Granger](https://img.shields.io/badge/Granger-causality-006400)

---

## Why this project

Macro analysis and asset analysis are usually done in different rooms. Economists identify cycle phases from GDP, inflation and employment. Quants model asset volatility from price series. Both are useful, and neither on its own tells an investor what to do.

The thesis asks whether joining them produces something actionable: if macro indicators can flag a phase transition, and if asset volatility regimes line up with those phases, then portfolio adjustments can be timed against the cycle rather than reacting after the fact. That is the hypothesis the whole analysis is built to test.

## Approach

The work splits into two halves that meet at the end.

**Fundamental analysis, identifying the cycle.** Macro indicators are used to detect expansion, peak, recession and recovery: GDP, short and long term interest rates, inflation through the GDP deflator, unemployment, PMI, VIX, the M3 monetary aggregate, and recession probabilities from Markov Switching models and the Sahm rule. Pearson correlations map the relationships between indicators, and Granger causality tests identify which of them carry genuine predictive signal rather than merely moving together.

**Technical analysis, modelling the assets.** Five assets spanning very different risk profiles: Bitcoin, gold, Brent crude oil, the S&P 500 and ROTX, the Romanian blue chip index. Prices are cleaned, tested for stationarity with ADF, KPSS and Phillips-Perron, and transformed into log returns. Then:

| Model | What it captures |
|-------|-----------------|
| ARIMA | Autoregressive and moving average structure in returns |
| GARCH and EGARCH | Conditional volatility, with EGARCH allowing asymmetric response to good and bad news |
| MS-GARCH | Volatility regimes (low, medium, high) and the probability of being in each, tied back to cycle phase |

Rolling forecasts and rolling Value at Risk are computed on top, which is where the two halves join: regime probabilities from the asset side get read against cycle phases from the macro side.

## Data

| Domain | Sources |
|--------|---------|
| Macroeconomic indicators | World Bank, Eurostat, Federal Reserve, National Bank of Romania |
| Bitcoin | CoinMarketCap |
| Gold, oil, S&P 500 | Yahoo Finance, Investing.com |
| ROTX | Bucharest Stock Exchange |

## Notebooks

| Notebook | Contents |
|----------|----------|
| [`Macroeconomic_Indicator_Analysis.ipynb`](Macroeconomic_Indicator_Analysis.ipynb) | Cycle phase identification, all macro indicators, correlation heatmap, Granger causality network |
| [`Financial_Assets_Analysis.ipynb`](Financial_Assets_Analysis.ipynb) | Stationarity tests, ACF and PACF, ARMA and ARIMA, ARCH-LM diagnostics, GARCH fitting, rolling forecasts, rolling VaR |
| [`Markov_Switching_EGARCH_in_R.ipynb`](Markov_Switching_EGARCH_in_R.ipynb) | ARIMA-GARCH and MS-GARCH in R, regime probability plots per asset |

## Findings

On the macro side, indicators gave clear signals at phase transitions, and the link between global monetary expansion through M3 and real GDP growth came through strongly.

On the asset side, the five assets behave in usefully different ways:

- **S&P 500 and ROTX** are pro-cyclical and highly sensitive to global liquidity conditions
- **Gold** behaves counter-cyclically, acting as a safe haven through recessions and crises
- **Bitcoin** shows extreme volatility with regime shifts driven by liquidity and sentiment shocks
- **Oil** follows a pro-cyclical pattern but is heavily exposed to geopolitical shocks, which often override the cycle

Taken together, the integrated framework supports the original hypothesis: watching macro indicators alongside asset volatility regimes gives enough warning to adjust a portfolio ahead of a transition, which improves risk adjusted returns compared with a static allocation.

## Stack

Python (pandas, NumPy, statsmodels, arch, scikit-learn, matplotlib, seaborn, networkx) and R (rugarch, MSGARCH, forecast, tseries, ggplot2).

## Keywords

Economic cycles, fundamental analysis, technical analysis, ARIMA, GARCH, EGARCH, MS-GARCH, Granger causality, Value at Risk, Bitcoin, gold, oil, S&P 500, ROTX.
