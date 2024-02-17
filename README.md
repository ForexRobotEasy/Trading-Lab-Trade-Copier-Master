# Trading Lab Trade Copier

This code is a trade copier that allows you to copy trades from a master terminal to multiple slave terminals. It is developed by the Forex Robot Easy Team and can be used for seamless trade copying in MetaTrader 5.

## Libraries Used
- Trade.mqh
- PositionInfo.mqh

## Constants
- MAX_SLAVES: Maximum number of slave terminals that can be connected
- MAX_SYMBOLS: Maximum number of symbols being traded

## Variables
- slavesCount: Number of slave terminals connected
- symbolsCount: Number of symbols being traded
- positionInfo: Object to retrieve position information
- trade: Object to perform trade operations

## Initialization
- The OnInit() function is called when the Expert Advisor is initialized.
- It initializes the trade copier settings using trade.Init().
- The number of slave terminals connected is obtained using trade.GetSlaveTerminalsCount().
- The number of symbols being traded is obtained using trade.GetSymbolsCount().
- Trade copying from master to slaves is enabled using trade.SetTradeCopying(true).
- Automatic adjustment of settings on slave terminals is enabled using trade.SetAutoAdjustment(true).
- Stop loss and take profit copying is enabled using trade.SetStopLossCopying(true) and trade.SetTakeProfitCopying(true).

## Trade Copying
- The OnTick() function is called on each tick.
- The current position on the master terminal is refreshed using positionInfo.Refresh().
- Trades are copied to all slave terminals using nested loops.
- The IsSymbolTraded() function is used to check if a symbol is being traded on the master terminal.
- If the symbol is being traded on both the master and slave terminals, the stop loss and take profit levels are copied using trade.CopyStopLoss() and trade.CopyTakeProfit().

## Account Management
- The ManageAccounts() function displays account information for all slave terminals.
- It uses trade.DisplayAccountInfo() to retrieve and display account information.

## Trading Control
- The ControlTradingActivities() function allows full control over Forex trading activities.
- It performs necessary trading actions such as opening a position, modifying the position, and closing the position.
- It uses functions like trade.OpenPosition(), trade.ModifyPosition(), and trade.ClosePosition().

## Code Optimization
- The OnDeinit() function is called when the Expert Advisor is deinitialized.
- It cleans up resources and terminates the trade copier using trade.Deinit().

Please note that ForexRobotEasy is not the official developer of this product. This code is a sample that can work as described in the product. To find the official developer of this product, please refer to MQL5.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy](https://forexroboteasy.com/forex-robot-review/trading-lab-trade-copier-review-seamless-metatrader-5-trade-copying/).
