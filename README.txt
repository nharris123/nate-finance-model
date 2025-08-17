README — Momentum + Volume Strategy Backtester
=============================================

How to use:
1) Place your OHLCV CSVs into ./data (one file per ticker, e.g. SPY.csv, AAPL.csv).
   Required columns: Date,Open,High,Low,Close,Volume.

2) Run:
   python3 momentum_volume_strategy.py

3) Outputs:
   - ./outputs/equity_curve.csv
   - ./outputs/trades.csv
   - ./plots/equity_curve.png

Strategy:
- Rank by weighted momentum: 12-month (60%) + 3-month (40%).
- Volume confirmation: recent 5-day avg volume > 1.3× 20-day avg,
  20-day average dollar volume ≥ $2M, price ≥ $3.
- Rebalance weekly into top 10 equal-weight names (≤12% cap).
- Risk controls: 3×ATR stops, 15% trailing stop, 1% cash buffer, 2 bps slippage.

This code is educational, not investment advice.
