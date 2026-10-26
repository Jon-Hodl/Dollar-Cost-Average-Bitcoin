# Dollar Cost Average Bitcoin

A worst-case scenario Bitcoin dollar-cost averaging (DCA) calculator.

**Live site:** `https://jon-hodl.github.io/dollar-cost-average-bitcoin/`

## What it does

This tool simulates a Bitcoin DCA strategy using intentionally pessimistic assumptions:

- **Every purchase** is made at the **daily high** price.
- **Final valuation** uses the **latest daily low** price.

If the numbers look good under these assumptions, the real-world outcome was almost certainly better.

## Features

- Adjustable investment amount
- Daily, weekly, or monthly purchase frequency
- Custom date range
- Summary stats: total invested, total BTC, current value, profit/loss, ROI
- Portfolio value chart vs. total invested
- Purchase history table

## Data source

Price data is pulled from the self-hosted **[Bitcoin Price Archive](https://github.com/Jon-Hodl/Bitcoin-Price-Archive)**.

No third-party APIs, no rate limits, no dependency on external price feeds.

## How it works

1. Fetches `prices.json` from the Bitcoin Price Archive.
2. For each purchase date, calculates BTC bought using the daily high:
   `btc_bought = investment / daily_high`
3. Sums total BTC accumulated and total fiat invested.
4. Values the portfolio using the latest daily low:
   `current_value = total_btc * latest_daily_low`
5. Displays ROI, charts, and history.

## Hosting

This is a static single-page app. It can be hosted on:

- GitHub Pages
- Any static web host
- Embedded as custom HTML in WordPress

## WordPress

To add this to `whatisbitcoin.com/tools/DCA-BTC`, paste the contents of `index.html` into a WordPress page using the Custom HTML block. Update the `PRICE_URL` if needed.

## License

MIT
