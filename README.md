# Momentum Investing

Investing is allocating resources, usually money, with the expectation of generating an income or profit. 
We will restrict ourselves with investment in the financial markets. Many strategies are created to assist the process of investment. Some strategies perform well and provide good returns (beating the market) and some fail to do so.
One such investing strategy is Momentum Strategy.
Momentum investing is a strategy that aims to capitalize on the continuance of existing trends in the market.
Momentum investing involves going long stocks, futures, market exchange traded funds (ETFs), or any financial instrument showing upward-trending prices and short the respective assets with downward-trending prices.

# Strategy:

In this project, I have calculated the cumulative historical 12 months returns. Based on these returns, bucketed the stocks in quantiles and longed the top quantile. Back-tested the strategy from 2010 to 2021, the strategy provided more than 4 times returns than nifty index.

After creating the equal weighted portfolio, estimated the portfolio's sensitivity (Beta) to market risk premium and Excess return, Alpha (Return not explained by market risk premium) using CAPM model. 

# Project:

Created a modular python based code (which takes user based investment parameters like, rebalancing period, investment start date and bucket size i.e. quantile/decile etc.),  applies the momentum strategy on NIFTY 50 (Indian Equity Index) stocks, and outputs the stock recommendations to invest on the investment start date. Here the investment date is end of each period starting from 2010-01-01 for example, month end dates for monthly rebalancing, quarter end dates for quaterly rebalancing and so on.

# Project Implementation

1. Rebalance period is taken as input from user which can be monthly , quaterly, half yearly or annually.
2. The return data is resampled based on the period provided by user.
3. Calculated the cummulative 12 months historical returns for each stock on rolling-basis (i.e. stock’s return over the months T-12 to T-1)
4. Calculated the cummulative future returns on rolling-basis (i.e. compound return over the next 'X' months, where X = 1, 3, 6 and 12)
5. Now, for each date, based on user input, sagregated the 12 months historical stock returns of firms into quantiles/deciles. Labelled the highest return bucket as UP and lowest return bucket as DOWN and remaining as NEITHER.
6. Create another dataframe with only UP labels and build an equally weighted portfolio for each date. 
7. Plot the cumulative returns for portfolio forward returns
8. Present the sharpe ratio and annual returns for the portfolio from 2010-01-01 to investment start date
9. Output the stock recommendation from the strategy based on investment start date
10. Estimated the portfolio's sensitivity (Beta) to market risk premium and Excess return, Alpha (Return not explained by market risk premium) using CAPM model.

# Results:

Period: 2010-01-01 to 2021-12-31

1. The momentum strategy provided sharpe ratio of 1.28 and average annual returns of ~24% on monthly rebalancing, i.e. nearly 3 times more returns than the index during the same period. The strategy increased the initial investment by 10 times from 2010 to 2021 while index fund increased it by 3.5 times.
