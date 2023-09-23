# Mahmoudos EMA & RSI % MFI Strategy

This README.md file explains the Pine Script code for the "Mahmoudos EMA & RSI % MFI Strategy." This strategy combines Exponential Moving Averages (EMA), Relative Strength Index (RSI), and Money Flow Index (MFI) to make buy and sell decisions in a trading algorithm.

## Overview

This Pine Script strategy aims to generate buy and sell signals based on the following components:

1. **EMA (Exponential Moving Average):** It calculates the Exponential Moving Average for a specified length. This EMA is used as a trend indicator.

2. **RSI (Relative Strength Index):** It calculates the RSI for a specified length and source price. RSI measures the strength of a price trend. If the RSI is high, it may indicate overbought conditions, and if it's low, it may indicate oversold conditions.

3. **MFI (Money Flow Index):** It calculates the MFI for a specified length using the high, low, and close prices. MFI measures the inflow and outflow of money in a security. High MFI values may indicate overbought conditions, while low values may indicate oversold conditions.

4. **Risk Management:** The strategy incorporates a risk management component that defines stop-loss and take-profit levels based on a percentage of the current price and a risk-reward ratio.

## Strategy Logic

The strategy's buy and sell logic is as follows:

1. **EMA Buy and Sell Triggers:** The EMA is used to generate buy and sell signals. It triggers a buy when the EMA is less than the closing price (`ema_buy_trigger`), and it triggers a sell when the EMA is greater than the closing price (`ema_sell_trigger`).

2. **RSI & MFI Buy and Sell Triggers:** The RSI and MFI are combined to create a single value (`rsi_mfi_result`). A buy is triggered when `rsi_mfi_result` is greater than or equal to 70 (`rsimfi_buy_trigger`), and a sell is triggered when it's less than or equal to 40 (`rsimfi_sell_trigger`).

3. **Stop Loss and Take Profit:** The strategy calculates stop-loss and take-profit levels based on user-defined parameters such as a percentage-based stop multiplier and a risk-reward ratio. These levels are used to manage risk in the trades.

4. **Entry and Exit:** The strategy executes long or short trades based on the combined signals from EMA and RSI/MFI. It enters a long position when both EMA and RSI/MFI triggers for a long trade are met. Conversely, it enters a short position when both triggers for a short trade are met.

5. **Exit from Positions:** The strategy exits positions using limit and stop orders based on the calculated stop-loss and take-profit levels.

## Parameters

The strategy can be customized using the following parameters:

- `emalength`: Length of the Exponential Moving Average (EMA).
- `rsilength`: Length of the Relative Strength Index (RSI).
- `rsiSource`: Source for RSI calculations.
- `mfilength`: Length of the Money Flow Index (MFI).
- `percent_based`: Percentage-based stop multiplier for calculating stop-loss levels.
- `r_ratio`: Risk-reward ratio for calculating take-profit levels.
- `qty`: The quantity of assets traded per order.

## Plotting

The strategy plots stop-loss (`SL long` and `SL short`) and take-profit (`T long` and `T short`) levels on the chart.

Please note that this strategy is a technical analysis-based trading strategy, and its performance should be thoroughly backtested before using it for live trading. It is essential to understand the associated risks and make informed decisions when using this strategy.

**Disclaimer:** This code is provided as-is and subject to the terms of the Mozilla Public License 2.0. The author and this document do not constitute financial advice, and any trading decisions made based on this code are at the user's own risk.
