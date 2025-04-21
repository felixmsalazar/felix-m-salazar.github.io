# Dynamic Regime-Aware ERC Portfolio Optimization
## Overview
This project develops an Equal Risk Contribution (ERC) strategy for investing in multiple assets, optimized dynamically based on changing market regimes. The framework integrates machine learning and advanced optimization techniques to enhance portfolio performance (Strategy backtest snapshots at the end).


## Framework Highlights
#### Core Innovation
Implement regime-aware ERC allocation using machine learning to detect market states.

Dynamically adjusts portfolio weights to balance risk contributions across assets.

## Framework Phases
## 1. Strategic Data Curation
#### Asset Selection: Focused on high-liquidity instruments with extensive historical data:

- Equity benchmark proxy (SP500)

- Sovereign debt exposure (T-Note)

- Inflation-sensitive commodity (Gold)

#### Feature Engineering:

- Volatility-normalized returns (log returns of 7 day MA) for noise-reduction data preprocessing.

## 2. Market Regime Inference Engine
#### State Space Architecture: Hidden Markov model (HMMlearn) with specific parameters:

- Dual-state hypothesis (e.g., bull/bear markets).

- State-specific volatility regimes.

- Adaptive covariance structures.

#### Machine Learning Operations:

- Recursive training protocol with drift correction (feedforward training with retraining steps avoid transition matrix stationarity).

- Asymmetric regime weighting methodology (bear state posterior probabilities).

## 3. Adaptive Optimization System
Regime-Sensitive Adjustments: Predicted regime probabilities influence portfolio weighting toward predicted high volatility market regimes by scaling covariance matrices by latent state posterior probabilities (bear state predicted probabilities).

Dynamic Covariance Modeling: Rolling covariance matrices recalibrated at each time step for responsiveness to market changes.

#### Optimization Objective: Minimize deviations from equal risk contribution across assets while adhering to constraints:

Long-only positions

No leverage

#### Solver: Utilizes a robust nonlinear optimization algorithm to solve the objective function efficiently.

## Testing Framework: 

#### Predicted Bear State Probability Weighted Portfolio 
![image](https://github.com/user-attachments/assets/9c3c4c58-175f-4269-9671-40911dee55e1)

#### Comparing in-sample and out of sample predicted state distributions for equity asset (0 = Bear, 1 = Bull)

![image](https://github.com/user-attachments/assets/6a777de2-db3a-4292-bd9e-9cc149236f3a)

#### Validating State Sequencing
Accurate state predictions visually confirmed with positive sloped green dot clusters and negative slope red dot clusters.

#### COVID Crisis
![image](https://github.com/user-attachments/assets/d3a4976f-7a95-4f73-8a7b-9b358ff7aef7)

#### Inflation Shock & Rising Rates
![image](https://github.com/user-attachments/assets/43a4bf49-aeb0-412f-98dd-9285915748c2)

