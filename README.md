# Stock-Price-Prediction-using-LSTM-and-ARIMA

Introduction
A stock in the most basic sense is a security which represents the ownership of a fraction of a company. Having stocks of a corporation makes the stock-holder entitled to a portion of the assets and profits of said corporation.
Stocks are predominantly bought on stock exchanges. Stock exchanges do not own shares but rather acts as a platform where the buyers of a stock can connect with the sellers. NYSE, NASDAQ, Borsa Istanbul can be listed as examples of an exchange.
The prices in the stock market are determined by supply and demand. Over time stocks have been able to outperform many other types of financial investments and still continue do so.
Analyzing and trading stocks to make profit is common practice nearly everywhere in the world. There are retail traders who may have different day-jobs while trading stock, there are professional traders and brokers whose sole income is the profit they make from trading. The high stakes nature of stock trading breeds needs for good mathematicians and statisticians to develop models to best analyze various aspects of stocks and make the best decision at the right time to either buy, sell or perform another more advanced action on the stock.
Quantitative analysis is a technique which uses mathematical modeling to understand behavior. In this case the behavior that is being investigated by quantitative methods is the behavior of the stock’s price. If the behavior of the stock can be predicted the party that predicted it can profit by trading. People who perform quantitative analysis for hedge funds and investment banks are usually referred to as “quants” and it’s usual that they out-earn most occupations on average including physicians. Quant hedge funds seem to have higher success than hedge funds who embrace orthodox trading strategies.
Machine learning is one of the more widely used methods by quants. Jim Simons, commonly referred to as “the most successful hedge fund manager of all time” admitted that him and his team used machine learning algorithms to make investment gains from market inefficiencies and that was what gave them the “edge” over other hedge funds. Even though now, machine learning is much more accessible due to MATLAB Toolboxes, Python libraries such as TensorFlow and PyTorch, machine learning can still be profitable to use for trading if the trader plays their cards correctly.
In this project I did exploratory data analysis on the AAPL (Apple), GOOG (Google), FB (Facebook), AMZN (Amazon) stocks’ historical data. Found how they correlate with each other and used two models (one deep learning and one regression) to predict the future price of GOOG.

Data Exploration
Data exploration is the backbone of any data science project. It is an initial look into the data to determine what techniques and methods should be used for maximum efficiency.
I started off my data exploration journey by plotting the respective day-closing price for each stock. The results were not at all surprising the closing price graphs looked very similar keep in mind the stocks I inspected were all big tech stocks. Then I looked at the trade volume per day data and the results were similar once again but not as much as the closing price.
 One of the favorite indicators of algorithmic traders is the moving the average so I calculated the moving average for every stock and visualized it against the Adjusted Closing price. The 10-day moving average data seemed to correlate more closely with the real price of the stock as expected.
The most important part of trading is profit as anyone would’ve guess. So I calculated and visualized the daily returns for each stock.
After the cookie cutter analyses were done I moved onto the heavier correlation analysis. Since all four stocks are of big tech companies medium to high correlation should be expected. I used the Daily Percentage Return as my main metric to calculate the correlation between these stocks. The final verdict was that all of the stocks were somewhat correlated with GOOG having the highest correlation with the other stocks. So I chose GOOG as the pivot stock to predict.
Price Prediction

LSTM
After doing research about which machine learning algorithms performed best for predicting the prices of securities I was set on using Long Short Term Memory (LSTM) as the main predictor for this project. Main reason why LSTM is considered the most successful model in a space where traditional models may not work that well is that LSTM Networks are Recurrent Neural Networks (RNN) which means they evaluate data based on the previous happenings. LSTM takes two inputs one current one that is the same input but lagged behind so that the model can be trained recurrently. RNN’s are similar to the human thought process.
When I trained my LSTM Network using the pre-determined GOOG price data it was a CPU intensive process and the training itself took 15 minutes every run. Optimizing was hard due to lack of computation power but I managed to work with what I had.
The result was somewhat satisfactory considering the lack of computational resources. The network could accurately predict the trend of the stock but the actual prices were higher than those predicted.

ARIMA
I decided to add another prediction method to supplement the LSTM Network, a method which could complement the RNN model. After doing research again ARIMA seemed to be best viable option to predict the price point of the stock without any worries about the trend which was sorted by LSTM.
ARIMA or Autoregressive Integrated Moving Average is a model that is widely used in econometrics for time series analysis. In this case the time series analysis was being done on the historical stock data.
ARIMA performed pretty similar to every other regression model, it was accurate at predicting the price but not so much in terms of the trend as expected.

Conclusion
Trading in a perfect market means that everyone has the same odds thus someone performing random trades should in theory be as successful as any other trader. However markets around the world aren’t close to perfect therefore educated traders and quants can take advantage of the imperfections. In this project I tried to predict the price point of a stock with what I would consider mild success. I am definitely planning build upon what I have built upon here. For the code and the documentation refer to the .mlx or the .pdf file.

Written by Uzay Karadağ
