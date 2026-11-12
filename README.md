
# Bitcoin Treasury & Equity Performance

## Corporate Bitcoin Reserves, Equity Valuation and Financial Risk Analysis Through Correlation, Cointegration and Statistical Arbitrage Techniques

A quantitative financial analysis project investigating how a company's strategic allocation of financial reserves to Bitcoin relates to its stock market performance, using statistical methods drawn from financial econometrics, statistical arbitrage and risk management.

## Project Overview

### Objective: Assessing the Financial Implications of Bitcoin as a Corporate Treasury Reserve

The project investigates the relationship between **corporate Bitcoin holdings and equity market performance**, using MicroStrategy (MSTR) as a case study.

MicroStrategy's decision to accumulate Bitcoin as a strategic treasury reserve represents an unconventional approach to corporate asset allocation, with significant implications for financial risk, market valuation and capital management.

While Bitcoin exposure may provide opportunities for capital appreciation, it also introduces substantial volatility and potential financial vulnerabilities, particularly when combined with leverage.

The analysis adopts a **corporate finance and treasury management perspective**, addressing questions relevant to a Chief Financial Officer (CFO):

- **Treasury allocation:** How closely does the company's equity valuation move with the market value of its Bitcoin exposure?
- **Financial risk:** To what extent might Bitcoin volatility influence shareholder value and amplify financial vulnerabilities?
- **Structural exposure:** Does the relationship between Bitcoin and the company's stock persist beyond short-term market fluctuations?
- **Risk management:** Can statistical relationships provide a foundation for investigating hedging strategies and managing prolonged market volatility?
- **Financial strategy:** What evidence can support decisions concerning treasury diversification, Bitcoin exposure and corporate financial resilience?

The project uses quantitative techniques commonly associated with statistical arbitrage to investigate these questions, rather than implementing an automated trading strategy.

## Analytical Framework

The methodology integrates two complementary statistical approaches:

**Pearson Correlation**

Measures the strength and direction of the linear relationship between Bitcoin and MicroStrategy market prices, supported by statistical significance testing.

**Cointegration Analysis**

Investigates whether the two non-stationary price series share a persistent equilibrium relationship, using Ordinary Least Squares (OLS) regression and the Augmented Dickey-Fuller (ADF) test on regression residuals.

Combining these methods enables the analysis to distinguish between observed price co-movement and evidence of a longer-term statistical relationship.

## Methodology

### 1. Market Data Acquisition and Comparative Performance

Historical market data are retrieved directly from Yahoo Finance for:

- **BTC-USD:** Bitcoin.
- **MSTR:** MicroStrategy equity.

The original analysis covers approximately one year of daily observations, from May 2024 to May 2025.

The notebook collects historical Open, High, Low, Close and Volume data, focusing primarily on closing prices.

The two series are aligned by trading date and normalized to a common initial value to enable direct comparison of their relative performance despite their different nominal price scales.

This provides an initial view of how Bitcoin price movements correspond to changes in MicroStrategy's market valuation.

### 2. Pearson Correlation and Statistical Significance

Pearson correlation is calculated to measure the linear association between the two closing-price series.

The analysis incorporates a statistical significance test to assess the strength of the observed relationship.

**Reported results:**

| Metric | Result |
|---|---:|
| Pearson correlation — closing prices | 0.9579 |
| P-value | 1.9630e-136 |
| Correlation — daily logarithmic returns | 0.6419 |

The exceptionally high closing-price correlation indicates strong positive co-movement over the observation period.

The correlation between daily logarithmic returns provides a complementary measure of the relationship between shorter-term price movements.

These results suggest substantial market sensitivity of MicroStrategy equity to Bitcoin price dynamics.

However, correlation alone does not establish causality or demonstrate that the relationship will remain stable under different market conditions.

### 3. Financial Time-Series Analysis and Stationarity Testing

The project extends the analysis beyond conventional correlation by investigating the statistical properties of the two financial time series.

The **Augmented Dickey-Fuller (ADF) test** is applied independently to Bitcoin and MicroStrategy closing prices.

The test evaluates whether the series exhibit stationarity, a relevant prerequisite for the subsequent cointegration analysis.

**Reported results:**

| Asset | ADF Statistic | P-value |
|---|---:|---:|
| Bitcoin | -0.7468 | 0.83426 |
| MicroStrategy | -1.2216 | 0.66422 |

Both series fail to reject the unit-root null hypothesis at the 5% significance level.

The findings are consistent with non-stationary price behavior, motivating further investigation into whether a linear combination of the two series exhibits a more stable statistical relationship.

The notebook also examines logarithmic return transformations and their distributions.

### 4. OLS Regression and Long-Term Relationship Estimation

The project applies **Ordinary Least Squares (OLS) regression** to normalized Bitcoin and MicroStrategy closing prices.

MicroStrategy is treated as the dependent variable and Bitcoin as the explanatory variable.

The regression estimates the statistical relationship between the two assets and generates residuals representing deviations from the fitted relationship.

**Reported regression results:**

| Metric | Result |
|---|---:|
| R-squared | 0.918 |
| Bitcoin regression coefficient | 2.3774 |
| Regression F-test p-value | 1.96e-136 |
| Durbin-Watson statistic | 0.238 |

The R-squared of 0.918 indicates that approximately 91.8% of the observed variation in normalized MicroStrategy prices is explained by the fitted linear relationship with normalized Bitcoin prices over the sample.

The estimated coefficient reflects the sensitivity of the normalized equity-price series to changes in the normalized Bitcoin-price series within this regression specification.

These results provide quantitative evidence of a strong historical relationship.

They do not, by themselves, establish a causal effect or a stable future hedge ratio.

### 5. Cointegration Analysis Using the Engle-Granger Approach

The central econometric component investigates whether Bitcoin and MicroStrategy share a longer-term equilibrium relationship.

The project applies a residual-based approach consistent with the **Engle-Granger two-step methodology**:

1. Estimate a linear relationship between the normalized price series using OLS regression.
2. Calculate the residuals, representing deviations from the estimated relationship.
3. Analyze the behavior of the residual series.
4. Apply the Augmented Dickey-Fuller test to investigate residual stationarity.

If the residuals are stationary, this provides evidence supporting cointegration between the two underlying non-stationary series, subject to the assumptions and appropriate statistical testing of the method.

**Reported residual ADF results:**

| Metric | Result |
|---|---:|
| ADF statistic | -3.2178 |
| ADF p-value | 0.0190 |
| Significance threshold | 0.05 |

The reported ADF test rejects the unit-root null hypothesis for the regression residuals at the conventional 5% level.

The notebook interprets this result as evidence supporting cointegration between Bitcoin and MicroStrategy.

The analysis also examines the behavior of the estimated spread and its deviations around the fitted equilibrium relationship.

**Methodological qualification:** the notebook uses a standard ADF test on OLS residuals. A formal Engle-Granger cointegration test requires cointegration-specific critical values. The reported result should therefore be regarded as supportive evidence rather than definitive proof of a persistent long-term equilibrium.

### 6. Statistical Arbitrage and Risk Management Implications

The project draws on the theoretical foundations of **statistical arbitrage and pairs trading** to interpret the relationship between the two assets.

In statistical arbitrage, cointegration can provide a basis for investigating temporary deviations from a historical equilibrium relationship.

These deviations may be relevant for evaluating:

- Relative valuation dynamics.
- Spread behavior and potential mean reversion.
- Market sensitivity to short-term shocks.
- Potential hedging relationships.
- Financial exposure monitoring.

In this project, these techniques are used primarily as **analytical tools for financial risk management**, rather than as an implemented trading system.

No executable pairs-trading strategy, transaction-cost analysis or out-of-sample trading backtest is presented.

## Corporate Finance and CFO Implications

### Treasury Reserve Allocation

The analysis provides evidence of the relationship between the market value of Bitcoin and the equity performance of a company adopting Bitcoin as a strategic treasury asset.

For corporate treasury management, this relationship is relevant when assessing the potential benefits and vulnerabilities of concentrating financial reserves in a volatile asset.

### Equity Valuation and Financial Exposure

The strong observed correlation suggests that Bitcoin price movements are closely associated with changes in MicroStrategy's market valuation.

This raises important questions about the interaction between treasury asset allocation, market expectations and shareholder value.

The analysis provides a quantitative starting point for examining these exposures.

### Leverage and Downside Risk

The notebook highlights the financial risks associated with significant Bitcoin exposure, particularly when leverage is involved.

A sharp decline in Bitcoin prices could increase financial pressure and adversely affect the company's market valuation.

The statistical analysis does not directly quantify leverage, liquidity coverage or solvency risk, but identifies a market relationship relevant to those broader financial considerations.

### Hedging and Financial Risk Management

Evidence of persistent statistical relationships can motivate further investigation into hedging strategies designed to manage exposure to Bitcoin-related market movements.

Potential applications include:

- Monitoring the sensitivity of equity valuation to Bitcoin.
- Investigating spread deviations and relative-value relationships.
- Evaluating possible hedging approaches.
- Supporting scenario analysis of adverse market conditions.
- Informing corporate treasury risk discussions.

These are potential applications of the analytical findings, not strategies that have been implemented or validated within the project.

### Strategic Financial Decision Support

The project demonstrates how econometric analysis can contribute to the assessment of unconventional corporate treasury strategies.

The findings can inform discussions about financial reserve concentration, risk tolerance, shareholder value and the resilience of treasury policies under volatile market conditions.

## Key Findings

**1. Strong Historical Relationship Between Bitcoin and MicroStrategy**

The closing-price correlation of 0.9579 demonstrates substantial positive co-movement over the analyzed period.

The relationship is also evident in daily logarithmic returns, although the correlation is lower.

**2. Significant Statistical Association**

The Pearson correlation and OLS regression results indicate a statistically significant historical association between the two market-price series.

**3. Evidence Supporting a Longer-Term Relationship**

The residual-based ADF analysis provides evidence consistent with cointegration, while requiring additional formal validation before drawing definitive conclusions about long-term equilibrium stability.

**4. Relevance for Corporate Treasury Risk Assessment**

The results highlight the importance of evaluating the market consequences of holding a substantial proportion of corporate financial reserves in Bitcoin.

**5. Potential Applications in Financial Risk Management**

The analytical framework offers a foundation for further investigation into treasury exposure monitoring, hedging and the management of Bitcoin-related financial risks.

## Technologies and Methodologies

**Programming and Data Processing**

Python · Pandas · NumPy

**Market Data**

Yahoo Finance · yfinance

**Financial Econometrics**

Pearson Correlation · Statistical Significance Testing · Time-Series Analysis · Ordinary Least Squares Regression · Augmented Dickey-Fuller Test · Residual-Based Cointegration Analysis

**Financial Applications**

Corporate Treasury Analysis · Financial Risk Management · Statistical Arbitrage Concepts · Pairs Trading Concepts · Relative-Value Analysis

**Statistical and Visual Analysis**

SciPy · Statsmodels · Matplotlib · Seaborn

**Development Environment**

Google Colab · Jupyter Notebook

## Project Files

- [Impact_of_Bitcoin_financial_reserve_in_MicroStrategy.ipynb](Impact_of_Bitcoin_financial_reserve_in_MicroStrategy.ipynb) — Complete analytical notebook, including market data acquisition, comparative performance analysis, correlation, OLS regression, stationarity testing and cointegration analysis.

### Data Sources

The notebook retrieves historical market data directly through Yahoo Finance:

- Bitcoin: `BTC-USD`
- MicroStrategy: `MSTR`

No external dataset files are required.

During execution, the notebook generates intermediate CSV files for data preparation and subsequent analysis.

The historical results presented in this README refer to the original observation period. Re-executing the notebook at a later date retrieves a new rolling one-year sample and may produce different results.

## Analytical Workflow

**Corporate Bitcoin Treasury Strategy → Market Data Acquisition → Comparative Equity Performance → Correlation Analysis → Stationarity Testing → OLS Regression → Residual-Based Cointegration Analysis → Treasury Risk and Financial Strategy Implications.**

The distinctive contribution of the project is the application of financial econometrics and statistical arbitrage concepts to a **corporate finance problem**, connecting market-price relationships with the strategic assessment of Bitcoin as a treasury reserve.

## Project Scope

Independent quantitative finance project examining the relationship between corporate Bitcoin reserves and equity market performance through statistical correlation, regression and cointegration techniques.

The project demonstrates how financial time-series analysis can provide evidence relevant to corporate treasury management, market exposure assessment and strategic financial decision-making.

The results are based on historical market observations and an experimental analytical framework. They do not establish causality, guarantee future statistical relationships or constitute a validated trading or hedging strategy.
