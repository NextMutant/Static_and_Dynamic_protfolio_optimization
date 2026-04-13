# Static-Portfolio-Optimizatio

This project implements **static portfolio optimization** using various criteria to optimize asset allocation in a portfolio. The optimization methods covered include:

- **Mean-Variance Optimization (MV)**
- **Mean-Variance-Skewness-Kurtosis Optimization (SK)**
- **Sharpe Ratio Optimization (SR)**
- **Sortino Ratio Optimization (SOR)**

## 1. Data Collection
The project uses the `yfinance` library to fetch historical adjusted closing prices for selected stocks (`META`, `NFLX`, `TSLA`). These are then processed to compute daily returns for optimization.

## 2. Portfolio Optimization Methods

### 2.1 Mean-Variance Optimization (MV)
- Optimizes the portfolio based on **expected return** and **variance**.
- Uses the `scipy.optimize.minimize` function to find optimal asset weights.
- Constraints: Weights sum to 1, weights are non-negative.
- Outputs an optimal portfolio allocation that maximizes the mean-variance criterion.

### 2.2 Mean-Variance-Skewness-Kurtosis Optimization (SK)
- Extends the **mean-variance approach** by incorporating **skewness (asymmetry of returns)** and **kurtosis (fat tails in the distribution)**.
- Uses a modified objective function to optimize higher-order moments of return distribution.

### 2.3 Sharpe Ratio Optimization (SR)
- Maximizes the **Sharpe ratio**, which is the ratio of return to volatility.
- Uses `scipy.optimize.minimize` to find optimal weights that maximize risk-adjusted returns.

### 2.4 Sortino Ratio Optimization (SOR)
- Similar to the **Sharpe ratio**, but considers only downside risk.
- Optimizes the **Sortino ratio**, which is the return divided by downside deviation (volatility of negative returns).
- More suitable for investors who care about downside risk rather than overall volatility.

## 3. Performance Evaluation
- After finding optimal weights for each method, we compute the **cumulative returns** for the test period.
- The performance of different optimization strategies is compared using:
  - **Sharpe ratio**
  - **Sortino ratio**
  - **Beta** (market sensitivity)
  - **Alpha** (excess return)
  - **Value at Risk (VaR)** and **Conditional VaR (cVaR)**
  - **Maximum drawdown**

## 4. Visualization
- The cumulative returns of different portfolios are plotted using `matplotlib`.
- The performance comparison is shown in graphical form to analyze which method works best.

## 5. Backtesting
- The `backtest_static_portfolio` function evaluates the portfolio's performance based on historical data.
- Outputs key portfolio metrics for decision-making.

## 6. Dependencies
Ensure you have the following Python libraries installed:
```bash
pip install numpy pandas scipy matplotlib yfinance
```

## 7. Running the Code
Simply execute the Python script, and it will:
1. Fetch historical data
2. Optimize the portfolio using different methods
3. Plot the cumulative return of each method
4. Display performance metrics
### **Tactical Portfolio Management – Brief Explanation**  

Tactical Portfolio Management involves adjusting stock positions dynamically based on quantitative strategies to maximize returns. This approach includes **shorting stocks, using momentum factors, and applying moving average and correlation-based strategies**.

---

### **Dynamic Methods**  
These are flexible trading techniques that adjust portfolio positions based on market conditions.  

- **Short a Stock:** Betting that a stock’s price will decline, allowing profit when the price drops.  
- **Momentum Factor:** Stocks with strong past performance are likely to continue performing well, and weak stocks tend to decline further.  
- **Rebalancing:** Adjusting portfolio allocations periodically to maintain the desired level of risk and return.  

---

### **Moving Average Strategy**  
This strategy helps in identifying trends using historical price data.  

- **Moving Average:** Computes the average stock price over a specific period to smooth out fluctuations.  
- **Moving Average Factor:** Compares short-term and long-term moving averages to determine buy/sell signals.  
- **Building the Strategy:** Buy when the short-term moving average crosses above the long-term moving average, and sell when it crosses below.  

---

### **Correlation Strategy**  
This strategy selects stocks based on their price relationships.  

- **Correlation:** Measures how stocks move relative to each other.  
- **Correlation Factor:** Analyzing past price trends to predict future returns.  
- **Building the Strategy:** Invest in stocks with a strong positive correlation and avoid or short stocks with a weak or negative correlation.  

These strategies help in **maximizing returns** while managing risk dynamically. 🚀

