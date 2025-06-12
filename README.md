# Backtest Strategies Framework  
[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)]()  

A modular engine for backtesting financial trading strategies with clear separation of data handling, strategy logic, execution simulation, and performance analytics – ideal for researchers and developers alike. :contentReference[oaicite:0]{index=0}  

## Table of Contents  
- [About The Project](#about-the-project)  
- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Project Structure](#project-structure) 

> Click the ☰ icon on GitHub to auto-generate this TOC for easy navigation.

## About The Project  
This framework provides:  
1. **DataHandler** that streams historical OHLCV data for one or more instruments.  
2. **Strategy** interface for implementing SMA/EMA crossovers, RSI triggers, drawdown-based rules, and more.  
3. **Portfolio** and **ExecutionHandler** modules simulating realistic order fills, slippage, and commissions.  
4. **Performance** analytics offering cumulative returns.
These components form a cohesive backtesting pipeline inspired by industry templates. :contentReference[oaicite:2]{index=2}  

## Features  
- Single- and multi-asset support  
- Vectorized indicators for high performance  
- Modular design for plug-and-play strategies  
- CI integration with GitHub Actions  
- Example Jupyter notebooks in `notebooks/`

## Installation  
1. Clone the repository:  
   ```bash
   git clone https://github.com/eddiesung111/my-backtest-strategies.git
   cd my-backtest-strategies
2. Create and activate a virtual environment (optional but recommended):
   ```bash
   python3 -m venv .env
   source .env/bin/activate
3. Install dependencies:
   ```bash
   pip install -r requirements.txt

## Usage
This section provides step-by-step instructions to get started with the Backtest Strategies Framework, including launching notebooks, running backtests via CLI, using the Python API, configuring via files, running tests, and troubleshooting. :contentReference[oaicite:0]{index=0}

1. **Launch the example notebook**  
   Start the Jupyter Notebook server in the project root and open the notebook located at `notebooks/Common_strategy.ipynb`. :contentReference[oaicite:1]{index=1}  
   ```bash
   jupyter notebook notebooks/Common_strategy.ipynb

2. **Run a backtest from the command line**
   Execute the backtest.py script with flags to specify the symbol, strategy, indicator parameters, and date range. 
   ```bash
   python src/backtest.py --symbol AAPL  --strategy sma \
   --fast-window 45 \
   --slow-window 180 \
   --start-date 2015-01-01 \ 
   --end-date 2024-12-31 \
   
3. **Use the Python API**
   Import the core classes from src/backtest.py and instantiate your data handler, backtest engine, and strategy to programmatically execute backtests.
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
   ```bash
   my-backtest-strategies/  
   ├── notebooks/              
   │   └── Common_strategy.ipynb  
   ├── LICNESE
   ├── .gitignore            
   └── README.md
   ```
