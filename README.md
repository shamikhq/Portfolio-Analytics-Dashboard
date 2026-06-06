# Portfolio Analytics Dashboard

An interactive dashboard for analyzing portfolio performance and risk, built in Python. Input a set of stock tickers and portfolio weights, and the dashboard visualizes returns, risk metrics, and correlations — benchmarked against the S&P 500.

Built as a summer project to develop skills in financial data analysis, quantitative risk metrics, and data visualization.

---

## Features

- Cumulative return chart vs. S&P 500 benchmark
- Drawdown chart showing peak-to-trough losses over time
- Correlation heatmap across all holdings
- Rolling 30-day volatility
- Summary metrics: annualized return, volatility, Sharpe ratio, Sortino ratio, max drawdown, alpha, beta
- Interactive UI — adjust tickers, weights, and date range in real time

---

## Tech Stack

- **Data** — `yfinance`, `pandas`, `numpy`
- **Visualization** — `plotly`
- **UI** — `streamlit`
- **Stats** — `scipy`

---

## Project Structure

```
portfolio-dashboard/
├── data.py          # Price fetching and returns computation
├── metrics.py       # Risk and performance metrics
├── charts.py        # Plotly chart functions
├── app.py           # Streamlit app entry point
├── requirements.txt
└── README.md
```

---

## Getting Started

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/portfolio-dashboard.git
cd portfolio-dashboard

# Create and activate virtual environment
python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run app.py
```

---

## Build Phases

### Phase 1 — Data Foundation ✅
Fetch historical adjusted closing prices via `yfinance`. Compute daily simple and log returns per ticker, build a weighted portfolio return series, and convert to a cumulative return index for charting.

### Phase 2 — Risk Metrics Engine 🔧
Pure functions for all key metrics: annualized return and volatility, Sharpe ratio, Sortino ratio, max drawdown, beta, and alpha vs. benchmark. Also includes rolling 30-day volatility and rolling Sharpe series.

### Phase 3 — Visualizations
Plotly charts for cumulative returns (portfolio vs. SPY), drawdown, correlation heatmap, rolling volatility, and portfolio weight allocation treemap.

### Phase 4 — Streamlit UI
Interactive dashboard wiring all charts and metrics together. Sidebar inputs for tickers, weights, and date range. Summary metric cards with benchmark deltas. Caching for fast re-renders.

### Phase 5 — Stretch Goals
- Efficient frontier via Monte Carlo simulation
- Fama-French 3-factor exposure regression
- Monte Carlo projected portfolio paths (10th / 50th / 90th percentile)
- Live holdings via Alpaca brokerage API

---

## License

MIT
