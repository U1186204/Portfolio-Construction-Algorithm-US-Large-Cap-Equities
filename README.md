# Portfolio Construction Algorithm for US Large-Cap Equities
**Authors**: _Adil Gazder, Chris Moreira, Danish Maknojia, Vishesh Gupta_


**Date**: December 11, 2024


**Affiliation**: Duke University - Fundamentals of Finance Business Models

## Abstract

This project introduces a portfolio construction algorithm tailored for US large-cap equities, designed to optimize Total Shareholder Return (TSR), manage volatility through equity beta, and allocate assets based on equity ratings. The resulting portfolio is diversified across 80 stocks from 8 distinct industries, ensuring low volatility and alignment with investor risk preferences. By integrating advanced quantitative methods, the algorithm delivers a portfolio with lower beta than the S&P 500 while adhering to stringent diversification constraints. Algorithmic portfolio management addresses inefficiencies in traditional asset allocation methods by leveraging data-driven processes. Inspired by sector-specific ETFs managed by leading asset managers, this project demonstrates how algorithmic systems can dynamically respond to market conditions while assuring diversification and performance. Algorithmic Science ultimately helps asset managers rebalance, automate, and seamlessly contruct equity porfolios. 

## Objective Functions
- Maximize Total Shareholder Return (TSR): Combining capital gains and dividend yield to comprehensively evaluate performance.
- Minimize Portfolio Volatility: Maintain an overall beta below 1.0 to ensure stability.
- Enhance Diversification: Apply constraints to industry and individual stock weightings to mitigate concentration risks.
- Optimize Allocation: Allocate weights using equity ratings derived from a combination of financial ratios and analyst assessments.
![image](https://github.com/user-attachments/assets/7b87679a-3f76-4a5e-b4cb-91043132ed5e)

## Key Variables
- Total Shareholder Return (TSR): A holistic performance metric accounting for both price appreciation and dividend yield, capturing the value delivered to shareholders.
- Equity Beta: A measure of stock volatility relative to the market, essential for constructing a portfolio with controlled risk.
- Equity Ratings (A to F): A comprehensive grading system evaluating financial metrics such as cash flow, debt ratios, and P/E multiples.

# Algorithm 
In the data preparation phase, TSR values were normalized across industries to ensure proportional representation. This normalization process adjusted each company's TSR so that its value reflected its relative contribution within its respective sector. Following normalization, a scoring mechanism was implemented, combining weighted grades and the normalized TSR values into a "Grade Score." The formula used for this computation was:
```scss
Grade Score = ((1 - y) * TSR) + (y * Grade Weight)
```
Here, the parameter y was assigned a value between 0.65 and 0.8, introducing controlled variability to ensure that the Grade Weight had a predominant influence in the final calculation while allowing for diversity in scoring outcomes.
Several constraints were integrated into the algorithm to maintain portfolio robustness. Industry allocations were capped at a maximum of 16% to prevent over-concentration, while individual stock weights were restricted to a maximum of 4.5% to minimize idiosyncratic risks. Additionally, the portfolio beta was constrained to remain below 1.0 to ensure stability and mitigate excessive market volatility.
The iterative process involved multiple steps to derive the optimal portfolio configuration. Initially, random weight generation introduced variability in weight calculations for each iteration. Grade scores were then calculated by combining TSR and Grade Weight to determine individual stock contributions. Subsequently, the weights were normalized to comply with the predefined industry and stock allocation constraints. The portfolio beta was computed as the weighted average of the individual stock betas to evaluate the portfolio's overall sensitivity to market movements. Finally, the algorithm selected the portfolio configuration with the lowest beta that satisfied all constraints, marking it as the optimal solution.

# Results
The algorithm achieved a portfolio beta of 0.89, representing a ~5% reduction compared to the S&P 500, while maintaining diversification. Over a 30-day evaluation period, the portfolio delivered a return of 10.08%, significantly outperforming both the S&P 500, which returned 5.98%, and all sectoral indices under consideration. The portfolio's diversification was evident in its balanced allocation across eight industries, with weights ranging from 9% for Real Estate to 15% for Finance and Technology. This project demonstrates the transformative potential of quantitative algorithms in constructing resilient, high-performing investment portfolios. By combining fundamental analysis with advanced optimization techniques, the algorithm delivers superior returns while maintaining stringent risk controls. The findings underscore the critical role of algorithmic portfolio management in modern finance and its capability to outperform benchmarks through innovative and disciplined approaches.
![image](https://github.com/user-attachments/assets/18d2bd3a-8554-48c4-9b76-5b74c5b208c1)
![image](https://github.com/user-attachments/assets/cbe15648-4c28-4568-9f33-ffb1950c2f18)

# Diversification Constraints Appendix
![image](https://github.com/user-attachments/assets/40e61869-f34f-4d4f-a9a6-b00b202ec942)
![image](https://github.com/user-attachments/assets/1e072ba9-0678-4a35-b2be-a5fd7e753abe)

