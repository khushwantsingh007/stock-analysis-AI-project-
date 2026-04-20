# Stock Trend Analysis

A web-based stock analysis dashboard built with Flask.  
It fetches real-time intraday market data, calculates technical indicators, and shows short-term price predictions.

## Features

- Live stock data fetch using `yfinance` (1-minute interval)
- Candlestick price chart with Plotly
- Technical indicators:
  - RSI (14)
  - MACD (12, 26, 9)
  - Bollinger Bands
- Simple forecasting models:
  - Linear Regression
  - Quadratic Regression
  - Cubic Regression
- Auto-refresh every 60 seconds

## Tech Stack

- Python
- Flask
- yfinance
- NumPy
- pandas
- scikit-learn
- Bootstrap 5
- Plotly.js

## Project Structure

```text
stock-analysis/
|- app.py
|- templates/
|  \- index.html
|- static/
|  |- css/
|  |  \- styles.css
|  |- js/
|  |  \- app.js
|  \- favicon.ico
\- README.md
```

## Setup and Run

### 1) Clone the repository

```bash
git clone https://github.com/khushwantsingh007/stock-analysis.git
cd stock-analysis
```

### 2) Create and activate virtual environment (recommended)

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3) Install dependencies

```bash
pip install flask yfinance numpy pandas scikit-learn
```

### 4) Run the app

```bash
python app.py
```

Open your browser at:

`http://127.0.0.1:5000`

## Usage

1. Enter a ticker symbol (example: `AAPL`, `MSFT`, `TCS.NS`)
2. Click **Analyze**
3. View:
   - Price candlestick chart
   - RSI, MACD, and Bollinger Bands tabs
   - Next 10-minute forecast

## API

### GET `/api/stock/<ticker>`

Returns JSON with:

- `prices` (OHLCV time series)
- `indicators` (RSI, MACD, Bollinger values)
- `predictions` (linear/quadratic/cubic)
- `last_updated`
- `news` (currently placeholder)

## Notes

- Prediction values are model-based estimates, not financial advice.
- Data availability depends on market hours and `yfinance` response.
