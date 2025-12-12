# Backtest Strategies Framework  
[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)]()  

A modular engine for backtesting financial trading strategies with clear separation of data handling, strategy logic, execution simulation, and performance analytics – ideal for researchers and developers alike.

## 📖 Table of Contents
* [About The Project](#about-the-project)
* [Features](#features)
* [Installation](#installation)
* [Usage](#usage)
* [Project Structure](#project-structure)
* [License](#license)

## 🔎 About The Project

This framework provides a cohesive backtesting pipeline inspired by industry templates:
* **`DataHandler`**: Streams historical OHLCV data for one or more instruments.
* **`Strategy`**: Interface for implementing SMA/EMA crossovers, RSI triggers, drawdown-based rules, and more.
* **`Portfolio` & `ExecutionHandler`**: Modules simulating realistic order fills, slippage, and commissions.
* **`Performance`**: Analytics offering cumulative returns and risk metrics.

## 🚀 Features
* **Multi-Asset Support:** Handles single and multi-asset portfolios.
* **Vectorized Indicators:** High-performance calculation using Pandas/Numpy.
* **Modular Design:** Plug-and-play architecture for swapping strategies.
* **CI Integration:** GitHub Actions ready.
* **Jupyter Ready:** Example notebooks included in `notebooks/`.

## Installation  
1. Clone the repository:  
   ```bash
   git clone https://github.com/eddiesung111/my-backtest-strategies.git
   cd my-backtest-strategies
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv .env
   source .env/bin/activate
3. Install dependencies:
   ```bash
   pip install -r requirements.txt

## Usage
This section provides step-by-step instructions to get started with the Backtest Strategies Framework, including launching notebooks, running backtests via CLI, using the Python API, configuring via files, running tests, and troubleshooting.

1. **Launch the example notebook**  
   Start the Jupyter Notebook server and open notebooks/Common_strategy.ipynb:
   ```bash
   jupyter notebook notebooks/Common_strategy.ipynb

2. **Run from Command Line (CLI)**
   Execute the backtest.py script with flags to specify symbol and strategy parameters:
   ```bash
   python src/backtest.py --symbol AAPL  --strategy sma \
   --fast-window 45 \
   --slow-window 180 \
   --start-date 2015-01-01 \ 
   --end-date 2024-12-31
   
3. **Use the Python API**
   Import core classes to run backtests programmatically:
   ```python
   from src.backtest import DataHandler, Backtest, SMA, Portfolio, ExecutionHandler

   dh = DataHandler("data/AAPL.csv")
   bt = Backtest(
      data_handler=dh,
      strategy_cls=SMA,
      strategy_params={"fast": 45, "slow": 180},
      portfolio_cls=Portfolio,
      execution_handler=ExecutionHandler(slippage=0.001, commission=1.0),
      starting_cash=10000
   )
   equity_curve = bt.run()
   print(equity_curve)


## Project Structure
   .
   ├── notebooks/              
   │   └── Common_strategy.ipynb  
   ├── src/
   │   ├── backtest.py
   │   └── strategies/
   ├── LICENSE
   ├── .gitignore            
   └── README.md

## 📄 License

This project is licensed under the MIT License.
