# Delta Hedging S&P500

## Project Steps

### Initial trades
- Download a six month window of adjusted close daily prices for the S&P500 (yahoo finance).
- Calculate annual volatility using 252 trading days
- Connect to Interactive Brokers via API and download the option chain for SPY
    - Source five contracts that are nearest to ATM, expiration roughly 30days out, have open interest, and have at least 1000 contract volume.
- Calculate the Black-Scholes price of the call options
- Sell 10 contracts of the call option with the largest mispricing
- Initiate a delta-hedge for the options, we'll rebalance daily to remain delta-neutral.

### Rebalancing
- Twice a day, rebalance so that risk-exposure remains as close to delta-neutral as possible
- Price the risk and compare against round-trip transaction costs of trading

### Assessment
After 4 weeks, the options will be exercised or expire with 0 value. Close the hedge position. Was this profitable?

## Data Pipeline
