# Markowitz-Portfolio-Optimization-using-Python


**Short description**

A Jupyter Notebook project that builds and analyses a Markowitz-style portfolio using historical price data (from Yahoo Finance) for a small basket of assets. The notebook calculates daily returns, annualized return and risk, portfolio-level statistics (return, variance, volatility), simulates random portfolios to plot the efficient frontier, and finds optimal portfolios (e.g., maximum Sharpe ratio, minimum variance). The NIFTY 50 index (^NSEI) is used as the benchmark.

---

## Assets used

The notebook downloads price data for the following tickers from Yahoo Finance:

* `HDFCBANK.NS` (HDFC Bank)
* `RELIANCE.NS` (Reliance Industries)
* `TATAMOTORS.NS` (Tata Motors)
* `ITC.NS` (ITC Limited)
* `GC=F` (Gold futures)
* `BTC-USD` (Bitcoin / USD)

**Benchmark:** `^NSEI` (NIFTY 50)

**Date range used in the notebook:** starts from `2021-01-01` (as set in the notebook).

---

## What the notebook does (high level)

1. **Data download and cleaning**

   * Downloads `Close` prices for the selected assets and the benchmark from Yahoo Finance using `yfinance`.
   * Aligns price series and handles missing data (shifts, drops or forward-fill depending on the code cell you run).

2. **Returns and summary statistics**

   * Computes daily returns (percentage change) and annualizes mean returns and volatility.
   * Computes covariance and correlation matrices of asset returns.

3. **Portfolio construction and simulation**

   * Generates random portfolio weights (e.g., using `np.random.random`) and normalizes them so they sum to 1.
   * For each simulated portfolio computes: portfolio return, portfolio variance (or volatility), and Sharpe Ratio (if a risk-free rate is considered in the notebook).
   * Repeats the simulation many times (e.g., thousands of portfolios) to build a cloud of portfolios for the efficient frontier.

4. **Finding efficient portfolios**

   * Identifies portfolios with **maximum Sharpe ratio** and **minimum variance** from the simulated set.
   * Optionally, computes and plots the efficient frontier and marks the optimal portfolios.

5. **Benchmark comparison**

   * Calculates returns and risk statistics for the `^NSEI` index for the same period and compares the user portfolio against the benchmark.

6. **Visualizations**

   * Price time series and normalized price chart (indexed to 100).
   * Histogram / bar charts of asset returns.
   * Efficient frontier scatter plot with optimal portfolios highlighted.
   * Bar chart of optimal portfolio weights.

---

## Files in this repository

* `Markowitz Portfolio Optimization.ipynb` — Main Jupyter Notebook (analysis, charts and calculations).
* `README.md` — This file.

---

## Requirements / Dependencies

Minimal required packages (use `pip install` or add them into a `requirements.txt`):

```
numpy
pandas
matplotlib
yfinance
scipy
jupyter
```


## How to run

1. Clone the repo and `cd` into it.
2. (Optional) Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate    # Linux / macOS
venv\Scripts\activate     # Windows
```

3. Install required packages:

```bash
pip install -r requirements.txt
# or individually e.g. pip install numpy pandas matplotlib yfinance
```

4. Launch Jupyter Notebook and open `Markowitz Portfolio Optimization.ipynb`:

```bash
jupyter notebook
```

5. Run the notebook cells in order. The first data-download cell uses Yahoo Finance; if you hit rate limits or missing data, re-run after a short wait or switch to smaller date ranges.

---

## Notebook structure / cell-by-cell overview

The notebook contains sections for:

* Imports and asset definitions (yfinance tickers & benchmark)
* Data download (`yf.download`) and construction of price / returns DataFrames
* Summary statistics (mean returns, std dev, correlation matrix)
* Portfolio simulation (random weights) and computation of portfolio statistics
* Efficient frontier plotting and selection of optimal portfolios (max Sharpe, min variance)
* Comparison against NIFTY 50 benchmark and final visualizations



## License

Choose an appropriate license for your GitHub repo (e.g., MIT License) and add a `LICENSE` file.

---

## Contact / Author

Name: Saksham Singh
Email: sakshams3198@gmail.com

