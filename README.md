# btc_price_prediction
Prediction of bitcoin prices using statistical ML.

Short summary:

Predicting the price of Bitcoin & other cryptocurrencies in general, is difficult in comparison to that of traditional investment options like stocks. The main reason for this is the high volatility associated with the price of Bitcoin. The price of a stock can be roughly predicted by studying the patterns & trends in its historical price whereas the price of Bitcoin is greatly influenced by market sentiments. News articles, tweets & the general perception of cryptocurrencies affect the price of Bitcoin to a great extent.
Due to this, we are considering the following predictors in this Machine Learning problem.
1. Historical price
2. Market sentiments

Objective:

To predict the direction of Bitcoin price movement for the next day. It should be noted that we are not trying to predict the absolute price for the next day. Because we will need a regression model to predict the absolute price and such a method tries to reduce the 'Mean-Squared-Error' metric to get the optimum model. This method can lead to predictions in the wrong direction of the actual price, which is not good. So, this is a classification problem based on time-series data.

Assumptions:

1. It is our assumption that the market sentiment has a strong influence on the price of Bitcoin - a causal relationship.
2. We are using the revision history of Bitcoin page in Wikipedia website and assume that the revision comments reflect the market sentiments.

Methodology:

Bitcoin belongs to the asset class of cryptocurrencies and we are trying to predict its price. In such cases, we need to consider the historical data on prices as the price of assets tends to follow trends. So, this Machine Learning project is a time-series problem and the predictors are historical prices & market sentiment.
The historical data on Bitcoin prices can be obtained from Yahoo Finance website. To understand the market sentiment, we need a proxy. This proxy can be obtained using sentiment analysis of tweets, news articles or google trends. In our problem, the sentiment analysis of the comments added when the Bitcoin page on wikipedia is revised is considered as a proxy of market sentiment. The sentiment of the comments is obtained by using a ready-to-use trained model of Transformer module.
In our problem, we use rolling averages of 'Close Price', number of wikipedia revisions on a day, overall sentiment for the day as predictors in a Random Forest classifier (baseline model) and later an XGBoost classifier.

Shortcomings:

We are training the model using the sentiments of comments added in wikipedia revisions, to predict the price of next day. This approach may not be optimal because the average sentiment for a day or percentage of negative sentiment may not be a good proxy for the general market sentiment. There is a high chance that wikipedia page is edited after a huge price swing has already happened.
Nevertheless, the approach used in this micro project is a good starting point to work further using a predictor that has a better causal relationship with Bitcoin prices.
