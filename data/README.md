# Position / return data

Daily regime position and return history for each single-asset 0/1 strategy, exported from the
walk-forward backtest notebooks in [regime-aware-allocation](https://github.com/xx2383/regime-aware-allocation)
(private repo; see that project's README for the methodology).

| File | Asset | Coverage (as of last export) |
|---|---|---|
| `SPX_positions.csv` | S&P 500 | 2007-01-04 to 2025-08-13 |
| `VBMFX_positions.csv` | Vanguard Total Bond Market Index Fund (Bloomberg US Aggregate Bond Index proxy) | 2007-01-03 to 2026-08-07 |
| `USD_positions.csv` | U.S. Dollar Index | 2007-01-02 to 2025-08-17 |

Each file has four columns:

- `DateTime` — trading day.
- `{ASSET}_Position` — the 0/1 regime call in effect that day (1 = bullish/long, 0 = bearish/flat),
  already shifted to avoid look-ahead: it reflects only information available as of the prior
  close.
- `{ASSET}_Return` — the asset's raw daily return that day (gross of any trading cost).
- `rf_daily` — the daily risk-free rate (3-month U.S. Treasury yield, compounded to a daily rate),
  used for Sharpe-ratio calculations.

The three files were exported at different times from their respective notebooks and are not
necessarily as of the same date — see the coverage column above. The live-updating SPX signal on
[the main page](../) refreshes daily; these CSVs are a static snapshot, not live-synced to it.
