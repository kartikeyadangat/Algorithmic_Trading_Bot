# Algorithmic Trading Bot

This repository contains a trading bot developed to execute a Moving Average Crossover Strategy on the Nifty 50 index and its stocks. The bot is built using Pine Script for strategy backtesting on TradingView and Python for integrating with the Zerodha trading platform via the KiteConnect API.

## Table of Contents
- [Strategy Overview](#strategy-overview)
- [Setup and Installation](#setup-and-installation)
- [Pine Script Strategy](#pine-script-strategy)
- [Python GUI Application](#python-gui-application)
- [Connecting to Zerodha](#connecting-to-zerodha)
- [Testing and Results](#testing-and-results)
- [Performance Analysis](#performance-analysis)
- [Contributing](#contributing)

## Strategy Overview
The trading strategy is based on the Moving Average Convergence Divergence (MACD) indicator, specifically designed for a 1-hour timeframe on Nifty 50 stocks. The strategy triggers buy signals based on moving average crossovers and MACD conditions. The bot then enters long positions with predefined target and stop-loss levels to manage risk effectively.

## Setup and Installation

### Prerequisites
- [TradingView Account](https://www.tradingview.com/)
- [Zerodha Account](https://zerodha.com/)
- [KiteConnect API Key](https://kite.trade/)
- Python 3.x
- Required Python Libraries: `tkinter`, `sqlite3`, `threading`, `kiteconnect`

### Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/kartikeyadangat/Algorithmic_Trading_Bot.git
   cd Algorithmic_Trading_Bot
   ```

2. **Install the required Python libraries:**
   ```bash
   pip install kiteconnect
   ```

3. **Generate KiteConnect API key and secret** using your Zerodha account and store them securely.

## Pine Script Strategy

### Overview
The Pine Script strategy calculates MACD on a 1-hour timeframe and filters signals based on a 1-day MACD for confirmation. It uses a combination of fast and slow moving averages, along with MACD crossover signals to determine entry points.

### Key Components
- **Moving Averages:** Calculated using user-defined `fastLength` and `slowLength`.
- **MACD Calculation:** Uses the `signalLength` to derive the MACD line and the signal line.
- **Buy Signal:** Triggered when the fast MA crosses above the slow MA, the MACD line is above the signal line, and the 1-day MACD is positive.
- **Risk Management:** Positions are exited based on a 3% target profit or a 2% stop-loss.

## Python GUI Application

### Overview
The Python GUI application interacts with the Zerodha trading platform, allowing users to place orders, track positions, and manage their portfolio. The application is built using `tkinter` for the interface and the `KiteConnect` API for trading functions.

### Key Features
- **Connect to Zerodha:** Authenticate using the KiteConnect API.
- **Place Orders:** Execute buy/sell orders based on the strategy’s signals.
- **Position Tracking:** Monitor open positions, including profit/loss in real time.
- **GUI Interface:** User-friendly interface to manage trading activities without needing to manually interact with the Zerodha platform.

## Connecting to Zerodha

1. **Generate API Key:** Log in to your Zerodha account and generate an API key via Kite Connect.
2. **Input API Key in Python Script:** Enter your API key and secret in the provided fields within the Python code.
3. **Authenticate and Start Trading:** Use the generated request token to authenticate and start trading via the GUI.

## Testing and Results

The strategy was thoroughly tested on TradingView and integrated with Zerodha using the Python GUI. A test trade using IOC stocks from the NIFTY50 list demonstrated the bot’s ability to buy and sell stocks autonomously based on the strategy's signals.

## Screenshots
Pine Script Backtest: Displays the buy and sell signals on the TradingView chart.
![image](https://github.com/user-attachments/assets/3a906755-6407-4754-9b11-139658b21fed)

Python GUI: Shows the interface for connecting to Zerodha and executing trades.
![Screenshot 2024-08-15 000040](https://github.com/user-attachments/assets/6dd920e1-6abc-4675-b3d0-eff31e7e66ad)


## Performance Analysis

### Metrics
The trading bot showed promising results during backtesting, especially with high-volume stocks from the NIFTY50. The bot effectively managed risk while maintaining a positive return profile. However, it is essential to regularly monitor and adjust the strategy to account for changing market conditions.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your proposed changes. For major changes, open an issue first to discuss what you would like to change.

