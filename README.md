# T.I.D.E. Engine
### Trending Index Dynamic Execution

## Overview
T.I.D.E. is an automated Python trading system engineered for live market execution. It runs monthly rotation checks across a 25-asset equities basket, calculating trailing 6-month momentum (127 trading days) via TwelveData API and executing market orders via Alpaca trading endpoints.

The core strategy logic was validated across historical stress periods before being connected to active broker APIs for forward paper-trading validation.

## Key Features & Architecture
- **Trailing Momentum Engine:** Pulls daily time-series market data to evaluate 6-month performance across 25 large-cap stocks (Tech, Healthcare, Finance, Energy, Consumer).
- **Risk Protection (Cash Fallback):** Automatically shifts target position to 100% CASH if top asset momentum falls to 0% or below.
- **Automated Order Pipeline:** Manages position rebalancing, market order placement, and position tracking via Alpaca broker endpoints.
- **Account & Event Logging:** Features a built-in `TradingAccount` class that tracks portfolio balance, logs P&L adjustments, and records trading events to local CSV logs.

## Tech Stack
- **Language:** Python 3
- **Data & APIs:** TwelveData API (Time Series), Alpaca REST API (Trading & Data)
- **Libraries:** Pandas, Requests, Datetime, Time
