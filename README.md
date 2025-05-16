# Algorithmic Trading Project

# Premise
My aim here is to gain experience with the research and implementation of a trading strategy. I aim to utilize a paper trading account, and over time analyze whether or not my
strategy will provide a theoretical profit. 


# Resources
I chose to use the Alpaca Trading API, which allows for easy access towards pulling historical data for various assets and to submit various types of
order requests on a paper trading account.


# Signal Theory
Given the high, low, and volume-weighted-average price of a stock indexed per minute over an arbitarty course of time, I wanted to find a way to quantify the price interval
of the stock over a certain interval while keeping track of potential price volatility. Therefore, by multiplying high and low price and scaling quadratically provides a volatility-adjusted range signal which will minimize large price swings while leaving more 'calm' intraday bars be. From here, my goal was to fit a linear regression model with this quantity as a predictor, and the following close price for the next minute as a prediciton target, in order to effectively try and 'predict' the price of the asset in the next minute.


# Targeted Assets
While I initially only intended to test this algorithm with highly volatile equities (such as AAPL, AMZN, etc.), I decided to provide functionality to test cryptocurrency assets as well, since they are traded 24/7, and I can therefore iron out bugs with my code at any time of day. Moreover, I feel like if I decide to add more strategies to this project as well, I can definitely work with cryptocurrencies in the future as well.


# Development Process
After pulling historical candle data mixed with vwap and trade volume for a stock/cryptocurrency over the past 100 minutes indexed by a minute timeframe, I calculated the corresponding signal column for each timeframe, as well as the following close price for the next timeframe. These two columns represented the inputs and  outputs of the linear regression model, respectively. I then used SkLearn to fit a linear regression model, and then predicted the next price for the asset, which would help me decide whether or not to buy another share of the asset or liquidate part of my position. The algorithim would then pause execution for 1 hour, before running again and pulling new data.


# Lessons Learned:
Throughout the development of this project, I learned more about signal extraction, feature engineering, and how to implement a trading strategy. I additionally gained more experience with Pandas, Sklearn, and the Alpaca API in general, and was given introductory exposure on how to analyze current time series data as well.


# Conclusion and Further Goals:
Overall, I'm quite happy with the development of my trading strategy, and will be sure to continue to update the page here with the performance of the algorithm. Additionally, as a further expansion to this project, I'd like to use Streamlit to eventually build a visualizer and potential backtester, as well as a user interface in order to test out this strategy with different assets while understanding how the strategy performs.
