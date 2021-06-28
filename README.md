# Dispersion-Trading-Strategy


# Objective: In this repository, we will create a dispersion trading strategy on the BankNifty index and its constituents.

# Background
Dispersion trading is a great way to profit by trading the implied correlation between implied volatility of an index and the implied volatility of the index constituents.
Trading signals can be generated based on the assumption that these implied correlation have a mean-reverting behavior which is why this strategy is on the category of correlation mean-reverting trading strategy. Hence, we will take positions when the implied correlation is greater than half standard deviation from the mean or when it is less than half standard deviation from the mean. In the case implied correlation is high, the index implied volatility is higher than that of the constituents implied volatility and we want to establish a short volatility position on the index and simultaneously assume a long volatility position on the constituents. Likewise, when the correlation is low, the index volatility is at a discount to the constituents, thus we want to establish a long volatility position on the index and assume a short volatility position on the constituents.

Recall that the index volatility is a market indicator which can be used for determining the market sentiments. In other words, the index volatility indicates if there is a stability in the market or not. By definition this indicator is measuring the change or volatility of the index, therefore if the indicator is high ,then we will expect more movements in the index. By the same logic, a high index volatility tells us that there is no typical trend in the index market due to the high fluctuations. If the index value is low, then it can be implied that there are not much fluctiations in the market and that the index is stable. Hence, depending of the value of the correlation, dispersion trading strategy can be carried out by going short (or long) on the index options and long (or short) on the options of the index constituents. Another important factor to keep in mind while executing this strategy is that dispersion trading requires all trades to be delta hedged so that the value of the given portfolio is not affected by the changes in the prices of the underlying assets.


# Methodology of the strategy

Below we can see the required data and the strategy idea on a nutshell.

## Data Required
    1. ATM strike price and implied volatility of the BankNifty index
    2. The bank stocks which comprise of at least 80% of the BankNifty index
    3. ATM strike price and implied volatility of the selected index constituents
    4. Weighted implied volatility of the selected index constituents
    5. Dirty correlation

## Mean Reversion Strategy
    1. Buy the index straddle and sell the index constituents’ straddle when the implied correlation is low
    2. Sell the index straddle and buy the index constituents’ straddle when the implied correlation is high
    3. Exit the positions when the implied correlation reverts to the mean



# Financial Data 

All options index data for the BankNifty index and its constituents( AxisBank, IciBank, HDFCBank, KotakBank, SBIN) was previously downloaded using the python library  
nsepy. Later, all data was merged and stored on a single csv file for reuseability purposes. The dates ranges from 07/2017 to 12/2017 and there might be duplicate data which will be and can be handled during the preprocess stage. 


# Conclusions
Final thoughts, dispersion trading is a complex strategy. However, this is rewarded with the strategy being a profitable one which offers high rewards in response to low risk. For this particular case, we saw the profitable gains achieved while executing the strategy. However, transactions fees were neglected and not considered on the PnL calculation. One thing to keep in mind is that the strategy could be improved by decrease the time interval to capture the implied volatility and accordingly dirty implied correlation. 
  

 
