# mams-v4-trading-system

MAMS-v4 — Multi-Agent Master Swing System

A multi-signal algorithmic trading system built in Pine Script for TradingView, designed for swing trading BTC and ETH on the 4-hour chart. Built entirely on my own time to learn how to apply quantitative and AI-assisted thinking to real financial markets.


What It Does

MAMS-v4 uses 13+ independent technical "agents", each evaluating a different aspect of market conditions, and aggregates their signals into a conviction score. Trades are only taken when enough agents align above a defined threshold, filtering out low-quality setups.

Key features:


Multi-agent signal aggregation with configurable long/short thresholds
Regime detection (Bull, Bear, Chop, Neutral) using EMA slope, ADX, and daily trend filters
Dynamic position sizing based on agent conviction count (8–20% equity)
Regime-adjusted take profit and stop loss multipliers
Volatility gate using ATR vs. 20-bar average to block entries in flat markets
ADX chop filter to avoid ranging conditions
Full alert system integrated with TradingView webhooks for automated execution


The development process looked like:


Research and define the signal logic I wanted each agent to evaluate
Write and test each component in isolation
Use AI to review logic, catch edge cases, and suggest improvements
Backtest, identify weaknesses, iterate
Add regime detection and dynamic sizing in a v4 upgrade
Build out webhook infrastructure (TradingView → VPS → Kraken via ccxt) for live execution



Outcome

The system has been backtested across 16 months of BTC/ETH data and is currently in live validation, working towards full capital deployment. It is consistently profitable with strong risk-adjusted returns and controlled drawdown.

Live execution infrastructure is fully built out and running on a DigitalOcean VPS with a Flask/Gunicorn webhook listener connected to Kraken via the ccxt library.


Tools Used


Pine Script v6 — strategy logic and TradingView alerts
Python — webhook server, exchange connectivity, live execution
Claude & ChatGPT — logic validation, debugging, iterative development
DigitalOcean — VPS hosting for live bot infrastructure
Kraken / ccxt — exchange API and order execution
