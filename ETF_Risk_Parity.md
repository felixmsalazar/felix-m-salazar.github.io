# Scalable & Optimized ETF Risk Parity Portfolio

## Idea

This project presents a novel approach to building a risk parity portfolio using ETFs. The goal was to construct a risk parity portfolio using liquid and cost-effective ETFs through simple optimization methods.

## Method

The investable universe comprises 24 U.S.-domiciled ETFs, offering exposure across diverse asset classes including U.S. equity sectors, rates, credit, securitized assets, commodities, and rate volatility. For offshore investors aiming to minimize income tax liability—particularly for the substantial fixed-income portion—the strategy can be implemented using UCITS ETFs.
In a risk parity portfolio, asset weights are determined such that each asset contributes equally to the portfolio's overall risk. The covariance matrix is crucial for calculating these weights as it quantifies risk and interdependencies among assets. I developed a function to compute rolling covariance matrices using a regime-switching model and Directed PCA (DPCA). These matrices capture dynamic correlations and volatilities of assets over time, potentially reducing estimation error compared to simple covariance matrices. By using rolling windows, the function accounts for changing market conditions, ensuring risk contributions are computed based on current market data.
The generated covariance matrices were used to solve for portfolio weights using risk parity optimization methods. These weights were then applied to construct and rebalance the portfolio monthly.

### Results

## Unlevered
The initial portfolio performed surprisingly well during the 5-year backtest period from 2019 to 2025, which included significant events like the COVID crisis and historic CPI increases.

![RP unlevered](https://github.com/user-attachments/assets/b400e969-d68b-4618-9f10-363e41e87b02)

The portfolio ("ETF Multi-Asset Portfolio") outperforms the traditional static 60/40 balanced portfolio (built using IVV and LQD). It demonstrates strong risk-adjusted performance with a Sharpe Ratio of 1.1976 and a Sortino Ratio of 2.5358. With annualized volatility of 6.6%, below the typical 10% target for such strategies, and a Sharpe ratio above 1, the strategy could be further leveraged to generate returns closer to broad equity indices with a higher Sharpe ratio.

![image](https://github.com/user-attachments/assets/7f05eb01-a580-417a-a984-3e8505480ce1)

## Levered
Leverage can be applied at the portfolio or asset level, with low variance assets typically being the best candidates for leveraging. My code design allowed for upstream asset-level weight modifications before portfolio reconstruction and Sharpe ratio calculations. For the leveraged portfolio, the goal was to increase Sharpe ratio and expected return with minimal leverage. This involved leveraging the commodity asset.

Highest Expected Return:
![image](https://github.com/user-attachments/assets/8d163247-e6e1-493b-81ab-4b11c3fb91a4)

Highest Sharpe:
![image](https://github.com/user-attachments/assets/d42668f7-d289-45fa-b8f0-8351a83b8983)

The levered allocation to the commodity asset was maintained at a constant exposure through the time series, yielding the following portfolio improvement:

![Levered Port TMET](https://github.com/user-attachments/assets/ff16e904-5ab0-4854-82be-8b956d927ac2)

The targeted use of leverage increases expected return while improving Sharpe despite increased risk.

![image](https://github.com/user-attachments/assets/553c7b03-68c3-4f69-a765-a8337507a779)

![TMET Dist](https://github.com/user-attachments/assets/2c0ea60b-82ad-4217-8b25-65bf8dc84279)

The targeted use of leverage increases expected return while increasing sharpe despite increase in risk. 

Finally, applying 2x leverage across the entire portfolio allows it to more closely resemble an all-equity index while maintaining a higher Sharpe ratio and lower volatility:

![2x port](https://github.com/user-attachments/assets/34b10c9d-d2ed-48ed-82c6-41a9e106bf19)

![image](https://github.com/user-attachments/assets/faf1f463-9d28-4950-8d22-86623fca0ffc)

We've effectively leveraged a scalable risk parity strategy to generate broad equity-like returns with lower risk. However, it's important to note that the use of leverage carries its own risks and may be uneconomical in practice due to associated costs.
