# T.I.D.E. Engine
### Trending Index Dynamic Execution

## Overview
I built T.I.D.E. as an automated Python momentum trading system designed for live market execution. It runs monthly rotation checks across a basket of 25 large-cap stocks, calculates trailing 6-month momentum (127 trading days) using the TwelveData API, and executes trades automatically through Alpaca endpoints.

Before connecting it to live broker APIs for paper-trading validation, I backtested and stress-tested the strategy logic across multiple historical market cycles, including the 2008 Financial Crisis.

## How It Works
- **Momentum Calculations:** Pulls daily historical prices across 25 equities (tech, healthcare, financials, energy, consumer) to calculate 6-month returns.
- **Cash Fallback:** If the top-performing asset has a momentum score of 0% or lower, the system shifts allocation to 100% Cash to protect capital.
- **API Order Execution:** Handles rebalancing, position tracking, and market orders via Alpaca REST API endpoints.
- **Logging & Tracking:** Includes a custom `TradingAccount` class that tracks equity balances, records P&L changes, and exports execution events to CSV.

## Tech Stack
- Python 3
- Pandas & NumPy
- TwelveData API & Alpaca REST API
