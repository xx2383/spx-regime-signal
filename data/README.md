# Position / return data

Daily position and return history of the S&P 500 regime strategy shown on the [main page](../), from the walk-forward
model in the paper "Regime-Aware Asset Allocation" (code: [regime-aware-allocation](https://github.com/xx2383/regime-aware-allocation)).

| File | Contents |
|---|---|
| `SP500_positions.csv` | Updated with the page: S&P 500 total-return index, 2007-01-03 to the latest close |

Columns of `SP500_positions.csv`:

- `DateTime`: trading day.
- `SP500_Position`: the main 0/1 position in effect that day (1 = hold the index, 0 = cash): the model's forecast
  from the prior close, confirmed over five consecutive days. It reflects only information available at the prior close.
- `SP500_Position_raw`: the unconfirmed daily forecast, lagged one day.
- `SP500_Return`: the index's daily total return that day (gross of trading cost).
- `rf_daily`: the daily risk-free rate (3-month U.S. Treasury yield, compounded to a daily rate).

The model matches the paper's except for one input: the bond leg of the equity-bond correlation feature is VBMFX (the
Bloomberg U.S. Aggregate index the paper uses is not publicly available), so these positions are close to, but not
exactly, the paper's (about 96% of the main-position days agree over 2007-2025-08).

`SPX_positions.csv`, `VBMFX_positions.csv` and `USD_positions.csv` are older static exports from an earlier version
of this project and are no longer updated.
