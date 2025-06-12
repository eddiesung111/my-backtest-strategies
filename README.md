# Backtest Strategies Framework  
[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)]()  

A modular engine for backtesting financial trading strategies with clear separation of data handling, strategy logic, execution simulation, and performance analytics – ideal for researchers and developers alike. :contentReference[oaicite:0]{index=0}  

## Table of Contents  
- [About The Project](#about-the-project)  
- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [Contributing](#contributing)  
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
