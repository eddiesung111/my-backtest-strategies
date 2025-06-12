# Backtest Strategies Framework  
[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)]()  

A modular engine for backtesting financial trading strategies with clear separation of data handling, strategy logic, execution simulation, and performance analytics – ideal for researchers and developers alike. :contentReference[oaicite:0]{index=0}  

## Table of Contents  
- [About The Project](#about-the-project)  
- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [License](#license)  

> **Auto-generated TOC** on GitHub when you click the table-of-contents icon – perfect for quick navigation. :contentReference[oaicite:1]{index=1}  

## About The Project  
This framework provides:  
1. **DataHandler** that streams historical OHLCV data for one or more instruments.  
2. **Strategy** interface for implementing SMA/EMA crossovers, RSI triggers, drawdown-based rules, and more.  
3. **Portfolio** and **ExecutionHandler** modules simulating realistic order fills, slippage, and commissions.  
4. **Performance** analytics offering cumulative returns.
These components form a cohesive backtesting pipeline inspired by industry templates. :contentReference[oaicite:2]{index=2}  

## Features  
- **Single- and multi-asset support**  
- **Vectorized indicators** for high performance :contentReference[oaicite:3]{index=3}  
- **Modular design** enabling plug-and-play strategies and broker models  
- **CI integration** with GitHub Actions for automated testing on every push :contentReference[oaicite:4]{index=4}  
- **Jupyter Notebooks** showcasing example strategies in `notebooks/Common_strategy.ipynb` :contentReference[oaicite:5]{index=5}  

## Installation  
1. Clone the repo:  
   ```bash
   git clone https://github.com/eddiesung111/my-backtest-strategies.git
   cd my-backtest-strategies

## Usage

This section provides step-by-step instructions to get started with the Backtest Strategies Framework, including launching notebooks, running backtests via CLI, using the Python API, configuring via files, running tests, and troubleshooting. :contentReference[oaicite:0]{index=0}

1. **Launch the example notebook**  
   Start the Jupyter Notebook server in the project root and open the notebook located at `notebooks/Common_strategy.ipynb`. :contentReference[oaicite:1]{index=1}  
   ```bash
   jupyter notebook notebooks/Common_strategy.ipynb

2. **Run a backtest from the command line**
   Execute the backtest.py script with flags to specify the symbol, strategy, indicator parameters, and date range. 
   ```bash
   python src/backtest.py --symbol AAPL --strategy sma --fast-window 45 --slow-window 180 --start-date 2015-01-01 --end-date 2024-12-31

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
my-backtest-strategies/  
├── notebooks/                # Jupyter/Colab notebooks  
│   └── Common_strategy.ipynb  
├── LICNESE
├── .gitignore                # Ignored files (envs, caches)  
└── README.md                 # Project overview and instructions

## License
**Key citations:**  
- GitHub README conventions (what to include) :contentReference[oaicite:11]{index=11}  
- Table of Contents auto-generation in GitHub UI :contentReference[oaicite:12]{index=12}  
- “Best README Template” for structure inspiration :contentReference[oaicite:13]{index=13}  
- Jehna’s README best-practices for features section :contentReference[oaicite:14]{index=14}  
- Hatica’s tips for visual elements/badges :contentReference[oaicite:15]{index=15}  
- Reddit guidance on README content and code snippets :contentReference[oaicite:16]{index=16}  
- Medium best practices for keeping docs updated and appealing :contentReference[oaicite:17]{index=17}  
- ChooseALicense.com instructions for MIT license :contentReference[oaicite:18]{index=18}
::contentReference[oaicite:19]{index=19}