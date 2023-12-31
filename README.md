#### Class Activity 1 Week 4: Student Portfolio Planner
##### Anvitha Chaluvadi

# **Portfolio Planner, Part 1**

Harold has been asked to research the following 10 stocks:

* Bank of New York Mellon (BK)
* Diamondback Energy (FANG)
* Johnson & Johnson (JNJ)
* Southwest Airlines Co (LUV)
* Micron Technologies (MU)
* Nike (NKE)
* Starbucks (SBUX)
* AT&T (T)
* Western Digital (WDC)
* Westrock (WRK)

Harold has been tasked with sorting stocks by risk/volatility; filtering out the top five stocks with the highest volatility and assigning the remaining stocks portfolio weights of 0.5, 0.2, 0.15, 0.10, and 0.05 (from least risk to most risk). He also needs to show the returns over time of a hypothetical $10,000 investment in such a portfolio.

Use the Pandas library to help Harold determine the risk profile of the 10 stocks, filter out the top-five highly volatile stocks, assign portfolio weights to each corresponding stock, and plot the returns of a $10,000 investment in such a portfolio over time.

## Instructions

Using the starter file, complete the following steps.

1. Import libraries and dependencies.

2. Read in the following CSV files:

    * `bk_data.csv`
    * `fang_data.csv`
    * `jnj_data.csv`
    * `luv_data.csv`
    * `mu_data.csv`
    * `nke_data.csv`
    * `sbux_data.csv`
    * `t_data.csv`
    * `wdc_data.csv`
    * `wrk_data.csv`

3. Combine the DataFrames so that the closing prices from each DataFrame are stacked column by column.

4. Use the `sort_index` function to sort the combined DataFrame by datetime index in ascending order (past to present).

5. Rename the columns to reflect the corresponding stock.

6. Use the `pct_change` function to calculate daily returns for each stock.

7. Use the `std` function and multiply by `sqrt(252)` to calculate annualized volatility. Use the `sort_values` function to quickly sort by volatility values.

8. Drop the top five stocks with the highest volatility from the DataFrame of daily returns.

9. Set portfolio weights of 0.5, 0.2, 0.15, 0.10, and 0.05 to the remaining stocks (from least risk to most risk). 

10. Use the `dot` function to multiply the weights by each column of daily returns to calculate the daily returns of the constructed portfolio.

11. Use the `cumprod` function to calculate the cumulative returns of the constructed portfolio.

12. Plot the returns of a hypothetical $10,000 investment in the constructed portfolio.

## Hint

To plot the returns of a $10,000 investment, multiply the initial investment by the portfolio's cumulative returns over time.

---

© 2022 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.


# **Portfolio Planner, Part 2**

Harold has been asked to revisit the 10 stocks that were researched in Part 1 of this activity: 

* Bank of New York Mellon (BK)
* Diamondback Energy (FANG)
* Johnson & Johnson (JNJ)
* Southwest Airlines Co (LUV)
* Micron Technologies (MU)
* Nike (NKE)
* Starbucks (SBUX)
* AT&T (T)
* Western Digital (WDC)
* Westrock (WRK)

Specifically, upper management wants Harold to go beyond just evaluating stocks by volatility/risk and create a more optimized portfolio with the following characteristics:

* Equal-weighted allocations

* Only the least correlated stocks

* Only positive return-to-risk ratio stocks (Sharpe ratios)

Then, they want to visualize the returns of a hypothetical $10,000 investment in such a constructed portfolio over time, as well as how such a portfolio compares to $10,000 investments in less optimized portfolios.

Use the Pandas library to help Harold construct an optimized portfolio of stocks, and then plot and compare the returns of a $10,000 investment in the portfolio over time to less optimized portfolios.

## Instructions

Using the starter file, complete the following steps:

1. Reset the DataFrame for daily returns of the 10 stocks. Use the `pct_change` function to calculate and reassign a new DataFrame of daily returns.

2. Use the `corr` function and the `heatmap` function from the `seaborn` library to calculate and visualize the stock return correlations for each stock pair.

3. Drop the two most consistently highly correlated stocks and keep the remaining less correlated stocks from the DataFrame (two stocks should be dropped). (*Hint: you can do this by visually identifying high correlations, or by summing then comparing total correlation values per stock.*)    

4. Use the `mean` and `std` functions to calculate the annualized Sharpe ratio and assess the reward-to-risk ratio of the 8 remaining, less-correlated stocks.

5. Drop stocks with the three lowest Sharpe ratios from the DataFrame (three stocks should be dropped).

6. Assess the investment potential of a noncorrelated (diversified) and return-to-risk (Sharpe ratio) optimized portfolio:

    * Set an equal weight for each stock in the optimized portfolio (five stocks). Use the `dot` function to multiply weights by each stock's daily returns to output the optimized portfolio's daily returns.

    * Calculate the optimized portfolio's cumulative returns, and then multiply the initial investment of $10,000 against the portfolio's series of cumulative returns. Plot the trend.

7. Assess the investment potential of a minimially correlated (diversified) portfolio:

    * Set an equal weight for each stock in a minimally correlated stock portfolio (eight stocks). Use the `dot` function to multiply weights by each stock's daily returns to output the noncorrelated stock portfolio's daily returns.

    * Calculate the minimally correlated stock portfolio's cumulative returns, and then multiply the initial investment of $10,000 against the portfolio's series of cumulative returns. Plot the trend.

8. Assess the investment potential of the original unoptimized portfolio:

    * Set an equal weight for each stock in an unoptimized portfolio (all 10 stocks). Use the `dot` function to multiply weights by each stock's daily returns to output the unoptimized portfolio's daily returns.

    * Calculate the unoptimized stock portfolio's cumulative returns, and then multiply the initial investment of `$10,000` against the portfolio's series of cumulative returns. Plot the trend.

9. Overlay the investment trend of every portfolio on a single chart, including the portfolio constructed in Part 1.

## Hint

Breathe easy! Take this activity one step at a time. Remember that this is the culminating activity of the unit. Think about the bigger picture in terms of what makes a particular stock portfolio a good investment.

---

© 2022 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.

