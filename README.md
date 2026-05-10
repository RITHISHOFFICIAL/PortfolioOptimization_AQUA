# Portfolio Optimization Engine

## Overview

This project is an algorithmic **Portfolio Optimization Engine** designed to construct risk-adjusted stock portfolios from the **Nifty 100 Index** using quantitative finance techniques.

The system automates:

* Stock universe collection
* Financial data preprocessing
* Portfolio optimization
* Risk management
* Backtesting and performance evaluation
* Visualization of portfolio characteristics

The project combines classical portfolio theory with modern quantitative optimization methods to build diversified and efficient portfolios.

---

# Objectives

The main goal of this project is to:

* Build optimized portfolios using quantitative methods
* Maximize risk-adjusted returns
* Reduce portfolio volatility and concentration risk
* Compare different optimization approaches
* Evaluate portfolio performance through backtesting

---

# Features

## Data Collection

* Fetches live Nifty index constituents
* Retrieves historical stock price data using Yahoo Finance
* Supports automated financial data extraction

## Data Cleaning & Preprocessing

* Handles missing values
* Removes assets with excessive missing data (>10%)
* Aligns benchmark and stock data properly
* Computes daily returns for optimization

## Portfolio Optimization

### Markowitz Mean-Variance Optimization

* Maximizes Sharpe Ratio
* Applies practical investment constraints
* Generates optimized stock allocations

### Hierarchical Risk Parity (HRP)

* Uses clustering-based allocation
* Reduces concentration risk
* Improves diversification stability

## Risk Management

* Ledoit-Wolf covariance shrinkage
* Maximum stock weight constraints
* Maximum sector exposure constraints
* Diversification-focused allocation rules

## Visualization

* Correlation heatmaps
* Portfolio weight distribution plots
* Performance comparison charts
* Risk-return visualization

## Backtesting Engine

Calculates:

* CAGR (Compound Annual Growth Rate)
* Sharpe Ratio
* Maximum Drawdown
* Portfolio cumulative returns

---

# Tech Stack

| Category                      | Tools / Libraries                        |
| ----------------------------- | ---------------------------------------- |
| Programming Language          | Python                                   |
| Financial Optimization        | PyPortfolioOpt                           |
| Data Manipulation             | Pandas, NumPy                            |
| Data Source                   | Yahoo Finance (yfinance), NSE Index Data |
| Visualization                 | Matplotlib, Seaborn                      |
| Machine Learning / Statistics | Scikit-learn                             |

---

# Project Architecture

```text
NSE Constituents + Yahoo Finance Data
                |
                v
      Data Cleaning & Alignment
                |
                v
       Returns & Covariance Matrix
                |
      -------------------------
      |                       |
      v                       v
Markowitz Optimization      HRP Optimization
      |                       |
      -------------------------
                |
                v
         Portfolio Weights
                |
                v
        Backtesting Engine
                |
                v
      Metrics & Visualization
```

---

# Data Pipeline

1. Fetch Nifty index constituents
2. Download historical stock prices
3. Clean missing and invalid data
4. Calculate daily returns
5. Estimate covariance matrix
6. Perform optimization
7. Generate portfolio allocations
8. Backtest strategy performance
9. Visualize portfolio insights

---

# Optimization Constraints

The portfolio includes several practical investment constraints:

* Maximum 10% allocation per stock
* Maximum 30% allocation per sector
* Covariance shrinkage for stable risk estimation
* Diversification-focused portfolio construction

---

# Performance Metrics

The project evaluates portfolios using:

| Metric             | Description                          |
| ------------------ | ------------------------------------ |
| CAGR               | Measures annualized portfolio growth |
| Sharpe Ratio       | Risk-adjusted return metric          |
| Max Drawdown       | Largest portfolio decline            |
| Volatility         | Standard deviation of returns        |
| Cumulative Returns | Overall portfolio growth             |

---

# Example Workflow

```python
# Fetch stock data
prices = download_data(tickers)

# Compute returns
returns = prices.pct_change().dropna()

# Optimize portfolio
optimizer = EfficientFrontier(mu, S)
weights = optimizer.max_sharpe()

# Backtest portfolio
results = backtest(weights, returns)
```

---

# Future Improvements (V2)

Planned future enhancements include:

* Machine learning-based return prediction
* Live trading API integration
* Automated portfolio rebalancing
* Reinforcement learning strategies
* Factor investing models
* Interactive dashboard deployment
* Multi-asset portfolio support

---

# Folder Structure

```text
Portfolio-Optimization/
│
├── data/                   # Raw and processed data
├── notebooks/              # Jupyter/Colab notebooks
├── visualizations/         # Generated charts and plots
├── backtesting/            # Backtesting modules
├── optimization/           # Portfolio optimization logic
├── utils/                  # Helper functions
├── requirements.txt        # Project dependencies
└── README.md
```

---

# Installation

## Clone the Repository

```bash
git clone <repository-url>
cd Portfolio-Optimization
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Required Libraries

```bash
pip install pandas numpy matplotlib seaborn yfinance pyportfolioopt scikit-learn
```

---

# Running the Project

1. Open the notebook in Google Colab or Jupyter Notebook
2. Run all cells sequentially
3. Review generated portfolio allocations and analytics
4. Analyze backtesting performance

---

# Key Concepts Used

* Modern Portfolio Theory (MPT)
* Mean-Variance Optimization
* Sharpe Ratio Maximization
* Hierarchical Risk Parity (HRP)
* Covariance Shrinkage
* Quantitative Risk Management
* Backtesting & Portfolio Analytics

---

# Applications

This project can be used for:

* Quantitative finance learning
* Portfolio construction research
* Algorithmic trading systems
* Investment strategy experimentation
* Risk management studies
* Financial data analysis projects

---

# Acknowledgements

* NSE India
* Yahoo Finance
* PyPortfolioOpt
* Pandas & NumPy communities
* Open-source quantitative finance ecosystem

---

# License

This project is intended for educational and research purposes.

---

# Author

Developed as a quantitative finance and portfolio optimization project focused on systematic investing and risk-adjusted portfolio construction.
