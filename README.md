## Overview
This project studies **time-varying volatility (risk)** in financial markets using a
GARCH(1,1) framework and compares it with **machine-learning–based volatility estimation**.
The focus is on **volatility clustering, regime behavior, and model robustness**
across calm and stress periods rather than return prediction or trading strategies.

The project is designed as a **risk and market dynamics analysis**, aligned with
quantitative finance and risk modeling practices.

---

## Data
- Market data: Daily closing prices of a liquid financial index (e.g., NIFTY 50)
- Prices are converted to **log returns**, which form the basis for all modeling
- Analysis spans multiple market regimes, including stress periods (e.g., COVID-19)

---

## Methodology

### 1. Exploratory Time Series Analysis
- Construction of log return series
- Visualization of return behavior and volatility clustering
- Rolling volatility used as an initial risk proxy

### 2. GARCH Volatility Modeling
- Fitted a **GARCH(1,1)** model to estimate conditional volatility
- Extracted time-varying volatility as a measure of market risk
- Compared GARCH volatility with rolling volatility
- Analyzed volatility behavior during stress periods

### 3. Volatility Regime Identification
- Classified market conditions into **Low, Medium, and High volatility regimes**
  using quantile-based thresholds
- Studied regime persistence, transitions, and regime-wise risk characteristics

### 4. Machine Learning–Based Volatility Estimation
- Used squared returns as a proxy for realized volatility
- Built ML features using lagged returns and lagged volatility
- Trained a simple ML model (Random Forest) using a **time-series–safe split**
- Generated out-of-sample ML-based volatility estimates

### 5. Model Comparison
- Compared GARCH and ML volatility estimates:
  - Overall error against realized volatility
  - Regime-wise performance
  - Stability vs noise characteristics
  - Behavior during stress periods

---

## Key Insights
- Financial market volatility exhibits strong **clustering and regime persistence**
- GARCH provides **stable and interpretable** volatility estimates, especially during
  high-volatility regimes
- ML-based models adapt more quickly but can be **noisier and less stable** during stress
- No single model dominates across all regimes, highlighting a trade-off between
  **robustness and flexibility** in risk modeling

---

## Limitations
- GARCH assumes a specific parametric structure and conditional distribution
- ML models are sensitive to feature choice and may overfit calm regimes
- Extreme market events challenge both parametric and ML-based approaches
- Volatility is inherently regime-dependent, limiting universal model dominance

---

## Technologies Used
- Python
- NumPy, Pandas
- Matplotlib
- arch (GARCH modeling)
- scikit-learn

---

## Disclaimer
This project is for **educational and research purposes only**.
It does not constitute financial, investment, or trading advice.
