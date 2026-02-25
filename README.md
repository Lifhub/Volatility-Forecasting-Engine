## Quantitative Risk Framework: Volatility Modeling & VaR Forecasting

### Project Overview
This repository features a comprehensive quantitative framework for modeling time-varying volatility and assessing market risk. Utilizing the **GARCH(1,1)** specification, this engine analyzes the stylized facts of financial time series, such as volatility clustering and fat-tailed distributions. The project concludes with a **Value-at-Risk (VaR)** backtesting suite to validate model performance under different market regimes.

### Key Highlights
- **Volatility Clustering:** Modeled the persistence of market shocks using GARCH specifications, confirming that $α+β≈1$.

- **Fat-Tail Accounting:** Implemented the **Student's t-distribution** for the error term to better capture the excess kurtosis ($ν$) inherent in equity markets, specifically for high-growth assets like Nvidia (NVDA).

- **Risk Metrics:** Generated daily **95% Parametric VaR** forecasts.

- **Backtesting Rigor:** Evaluated model accuracy by calculating the **Breach Ratio**, ensuring the empirical failure rate aligns with the theoretical confidence level.

### **Mathematical Methodology**

#### **1. GARCH(1,1) Specification**
We model the time-varying nature of market risk where the conditional variance $\sigma^2_t$ is dependent on a constant intercept, past shocks (ARCH), and past variances (GARCH):

$$\sigma^2_t = \omega + \alpha \epsilon^2_{t-1} + \beta \sigma^2_{t-1}$$

#### **2. Parametric Value-at-Risk (VaR)**
To forecast potential losses, we utilize the conditional volatility $\sigma_t$ and the inverse cumulative distribution function of the Student's t-distribution ($t^{-1}_{\nu}$) to account for fat tails ($\nu$):

$$VaR_{1-\alpha} = \mu + \sigma_t \times t^{-1}_{\nu}(\alpha)$$

Technical Stack
Language: Python

Quantitative Libraries: arch (GARCH modeling), yfinance (market data), pandas, numpy, matplotlib.

Methodology: Maximum Likelihood Estimation (MLE), Time-Series Backtesting.

Note on Data Scaling
To ensure numerical stability and convergence of the GARCH optimizer, log returns were scaled by a factor of 100 ($r_t$ × 100), as recommended for low-volatility financial time series.
