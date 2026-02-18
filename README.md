# Volatility Forecasting Engine

This repository contains a specialized framework for modeling financial time-series volatility, developed as part of my preparation for advanced studies in Financial Engineering at Université Paris Dauphine | PSL.

## 📊 Project Overview
The engine focuses on capturing stylized facts of financial markets, specifically **volatility clustering** and **leverage effects**, to improve the accuracy of market risk metrics.

## 🛠 Features
- **Data Acquisition:** Automated ETL from Yahoo Finance using `yfinance`.
- **Statistical Testing:** Implementation of Engle's ARCH test for heteroskedasticity.
- **Volatility Modeling:** GARCH(1,1) and EGARCH specifications using Student's T distribution.
- **Risk Application:** Daily 95% and 99% Parametric Value-at-Risk (VaR) forecasting and backtesting.

## 🚀 How to Use
1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`
3. Run the `Volatility_Engine.ipynb` Jupyter Notebook to view the full analysis and visualizations.

## 📈 Key Methodology
The project utilizes the `arch` library to estimate conditional variance. The primary goal is to demonstrate the persistence of shocks in financial returns and validate the model's predictive power via VaR backtesting.
