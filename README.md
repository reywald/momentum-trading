# Momentum Trading Platform

A Django-based algorithmic trading application designed to identify and execute momentum trading strategies in a paper-trading environment. The project is built in Python and is intended to integrate with Alpaca for brokerage and market data access, enabling backtesting, signal generation, and automated trading decisions without risking real capital.

## Overview

This application focuses on momentum trading, a strategy that buys assets showing strong upward price momentum and sells or avoids assets with weak trend performance. The system will:

- Connect to an Alpaca paper trading account for simulated execution
- Fetch market data from a reliable data provider
- Compute momentum indicators and trading signals
- Rank candidate assets based on trend strength
- Generate buy and sell decisions based on strategy rules
- Monitor positions and portfolio exposure
- Provide a web dashboard for strategy management

## Architecture

The project is structured as a Django web application with Python-based trading logic. Key components include:

- Django app for user authentication, dashboard, and strategy configuration
- Trading service layer for order execution and portfolio tracking
- Data ingestion layer for fetching historical and live market data
- Signal generation module for momentum indicators and screening logic
- Risk management rules for position sizing and exposure limits
- Paper trading integration with Alpaca

## Trading and Data Integration

This project is designed to use Alpaca as the broker for paper trading operations. In practice, Alpaca provides a broker API and market data access, which makes it a strong fit for a Django-based algorithmic trading workflow.

A more accurate setup is:

- The app connects to an Alpaca paper trading account for order execution and account data.
- Market data is obtained through Alpaca Market Data or a dedicated provider such as Polygon, depending on the selected data plan.
- SnapTrade is not needed for this project unless you want to connect and aggregate accounts from multiple brokers. For an Alpaca-focused trading app, direct integration with the Alpaca API is the standard approach.

## Strategy

The momentum strategy may include signals based on:

- Relative strength over a defined lookback period
- Moving average crossovers
- Price breakout conditions
- Trend persistence and volatility filters
- Risk-adjusted ranking across a watchlist of assets

The implementation can start with a simple, rule-based strategy and evolve into a more advanced research workflow with parameter optimization and strategy monitoring.

## Paper Trading

The system is intended to operate in paper trading mode so that trades are simulated in a sandbox environment rather than executed against real funds. This allows for:

- Safe strategy testing
- Real-time monitoring without financial risk
- Iteration on trading logic and risk controls
- Validation of execution flows before live deployment

## Tech Stack

- Python
- Django
- PostgreSQL (recommended for storing strategy data and trade logs)
- Celery (optional, for asynchronous tasks and scheduled jobs)
- Alpaca API
- Pandas / NumPy / TA-Lib or equivalent technical analysis libraries
- Plotly or similar visualization library for charts and analytics

## Project Goals

The goal of this project is to build a practical algorithmic trading platform that combines Django's web capabilities with Python-based quantitative trading logic. It will serve as a foundation for researching, testing, and automating momentum-based strategies in a controlled paper trading environment.

## Getting Started

1. Create a virtual environment.
2. Install dependencies with uv.
3. Configure environment variables for Alpaca API keys and app settings.
4. Set up the Django project and database.
5. Implement the data fetcher and momentum signals.
6. Integrate Alpaca paper trading execution.
7. Run the app locally and monitor trade activity.

## Notes

This project is for educational and research purposes. Trading strategies and market data should be validated carefully before any transition to live trading. Paper trading is useful for simulation, but it does not eliminate the need for sound risk management and strategy testing.
