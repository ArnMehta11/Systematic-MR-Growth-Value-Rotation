# Systematic-MR-Growth-Value-Rotation

**TLDR;** Systematic research framework for growth-value mean reversion across Tech-Retail equity pairs. Implements rolling, EWMA, and adaptive z-score signals with walk-forward calibration, cost-aware backtesting, regime stress tests, and cross-grid parameter sweeps to evaluate robustness, Sharpe persistence, and drawdown behavior.

**Project Description**
This repository contains a quantitative research framework focused on studying short term mean reversion between growth and value equities using a relative value and market neutral approach. The research is motivated by the observation that growth stocks, particularly within technology, can become overcrowded over short horizons, leading to temporary valuation distortions. When these positions unwind, capital often rotates toward value oriented sectors such as retail, creating potential opportunities for systematic relative value strategies.

The primary objective of this project is research rigor rather than signal mining. The framework is designed to test whether observed mean reversion effects are economically meaningful, statistically robust, and persistent across market environments. Emphasis is placed on avoiding look ahead bias, controlling for overfitting, and evaluating performance under realistic trading frictions. Strategies are assessed not by peak performance, but by their stability across parameters, time periods, and cost assumptions.

The research implements a pair based construction where growth and value equities are combined into dollar neutral spreads. Relative price relationships are normalized using rolling and exponentially weighted statistics, and mean reversion speed is estimated dynamically using walk forward half life models. Signals are generated using adaptive z score thresholds that respond to changing volatility and regime conditions rather than fixed parameters calibrated on the full sample.

Backtesting is conducted at a daily frequency using a full cross grid of parameters across signal methods, window lengths, and entry thresholds. The backtest engine explicitly models transaction costs including slippage, commissions, and short borrow costs. Scenario analysis is used to stress test strategies under increasingly adverse cost assumptions to understand how performance degrades as implementation frictions rise. This approach helps distinguish strategies that rely on fragile microstructure effects from those with genuine economic edge.

Performance evaluation focuses on risk adjusted and downside aware metrics. Annualized return, volatility, Sharpe ratio, Sortino ratio, and maximum drawdown are analyzed both at the individual pair level and in aggregated portfolios. Results are filtered to retain only the best performing configuration per pair in order to reduce multiple testing bias. Additional diagnostics are used to assess whether performance is driven by a small number of outlier periods or remains stable across regimes.

The design philosophy of the repository reflects institutional research standards. No single backtest is treated as decisive, and parameter robustness is prioritized over optimization. Costs are treated as first class constraints rather than afterthoughts. The framework is modular and extensible, allowing additional signals, regime definitions, or asset universes to be incorporated without altering the core methodology.

This repository is intended for quantitative researchers, systematic equity and relative value strategists, and students seeking exposure to hedge fund style research practices. It is particularly suited for those interested in building and evaluating market neutral strategies with an emphasis on robustness, implementation realism, and disciplined empirical testing.

This project is for research and educational purposes only and does not constitute investment advice or a recommendation to trade any security.
