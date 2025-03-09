Dynamic Regime-Aware Portfolio Optimization
Overview
This project develops an Equal Risk Contribution (ERC) strategy for investing in multiple assets, optimized dynamically based on changing market regimes. The framework integrates machine learning and advanced optimization techniques to enhance portfolio performance.

Framework Highlights
Core Innovation
Implements regime-aware risk parity allocation using machine learning to detect market states.

Dynamically adjusts portfolio weights to balance risk contributions across assets.

Framework Phases
1. Strategic Data Curation
Asset Selection: Focused on high-liquidity instruments with extensive historical data:

Equity benchmark proxy

Sovereign debt exposure

Inflation-sensitive commodity

Feature Engineering: Developed proprietary transformations, including:

Volatility-normalized returns

Adaptive trend extraction

Noise-reduction preprocessing

2. Market Regime Inference Engine
State Space Architecture: Customized hidden Markov model with:

Dual-state hypothesis (e.g., bull/bear markets)

State-specific volatility regimes

Adaptive covariance structures

Machine Learning Operations:

Recursive training protocol with drift correction

Real-time regime probability estimation

Asymmetric regime weighting methodology

3. Adaptive Optimization System
Regime-Sensitive Adjustments: Predicted regime probabilities influence portfolio weights to reflect varying risk-return dynamics.

Dynamic Covariance Modeling: Rolling covariance matrices recalibrated at each time step for responsiveness to market changes.

Optimization Objective: Minimize deviations from equal risk contribution across assets while adhering to constraints:

Long-only positions

No leverage

Solver: Utilizes a robust nonlinear optimization algorithm to solve the objective function efficiently.

Key Innovations
Regime-sensitive covariance modeling

Rolling horizon risk budget allocation

Adaptive position sizing based on:

Predicted state persistence

Cross-asset volatility clustering

Historical regime performance

Technical Architecture
Python-based quantitative stack

Custom HMM configuration layer

High-performance optimization libraries

Automated backtesting infrastructure

Strategic Outcomes
Enhanced risk-adjusted returns through proactive adaptation to regime shifts.

Improved portfolio resilience via dynamic allocation adjustments.

Systematic balancing of risk contributions across diverse assets.
