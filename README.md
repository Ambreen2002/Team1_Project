# UofT SCS FinTech Boot Camp Project 1

### For this project we examined four different portfolio management strategies (using the underlying S&P500 universe), which represent portfolios an investor might self select or pay to invest in. The chosen time period for our analysis is 2012 to 2017, selected as it is recent enough, covers a few different market condition, and accessible with publicly available data. 

Portfolios analyzed:
Base Case - Assumes investment in S&P 500 in market cap weights (using SPY ETF as a proxy)

Low Beta Portfolio - Rank stocks in S&P 500 and pick the 50 lowest beta stocks in equal weights.

High Beta Portfolio - Rank stocks in S&P 500 nd pick the 50 highest stocks in equal weights.

Randomly Generated - Randomly select 50 stocks from S&P 500 universe.

Tools/technologies used:
- Initially used Alpaca API for procuring financial price data, but pivoted to use yfinance library (based on Yahoo finance data)
- pandas
- seaborn (for correlation visualization)
- hvplot for visualization)
- numpy (for calculation of portfolio statistics)

Data preparation and cleaning:
- #### Imported historial S&P 500 price data from yfinance
- #### Checked for duplicates, nulls, and cleaned data sources as relevant, following which the clean data set was added to a csv file to ensure ease of processing
- #### Calculated betas for each security in resulting S&P 500 universe (includes all stocks with full performance history from 2012 to 2017 - stocks without the full performance history were not included in our analysis)
- #### Created portfolios based on criteria and stored them in dataframes in preparation for the analysis

Analysis completed:
- #### Montecarlo simulation in order to project the possible paths of return for each portfolio over the next two trading years. Conclusions: there is a wide potential range of outcomes, with potential for any given portfolio to perform better
- #### Calculated the cumulative return of each portfolio from 2012 to 2017 (and the growth of a $10k investment in each). Conclusions: The low beta portfolio produces the greatest cumulative profit, the high beta portfolio produces the lowest cumulative profit (including relative to the index). Random portfolio results differ depending on the simulation, but are designed to show that a stock picker selecting 50 different stocks could have a wide variety of returns outcomes.
- #### Calculated Sharpe ratios for each of the portfolios in order to assess which is best on a risk adjusted basis: both high and low beta portfolios have slightly better risk adjusted returns than the benchmark portfolio. Random portfolio selection differs depending on the scenario. Despite being more volaility from a returns perspective, the low beta portfolio offered better risk adjusted returns from 2012 to 2017, than the other portfolios.
- #### Calculated correlation of daily returns for each portfolio - - as anticipated, the high beta portfolio is more closely correlated with SPY (.96) than the low beta portfolio (.86); it is worth noting that given each is a sub-selection of the S&P500, both portfolios, as well as the random portolio, are highly correlated with the index returns

Conclusions?
In some circumstances a portfolio of selected securities may outperform the index over time, but that is not always the case, and in some cases the difference may be marginal and highly variable from portfolio manager to portfolio manager (i.e. random portfolio). It is difficult to predict what this outperformance might be, and montecarlo analysis shows us the outcome can be highly variable. Close due diligence and making sure any incremental costs of investing (fees) are worth the difference in returns when thinking about different portfolio strategies.

Further opportunities for analysis would include a broader set of data, other portfolio criteria, and different time frames and investment timelines.