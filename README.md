# Model performance tracking
| Date  | Change                          | MSE Interval 1|Interval 3|Interval 5|Interval 10| Description |
|-------|---------------------------------|----------------|-------------|----|----|----|
|06/28|Base line|1.142|||5.587|normalize each symbols with MinMaxScaler, train_set from 2017-06-01 till 2017-12-31, mse score of 'A'|
|06/28|1. keras normalization experiment|||||I want to finalize which normalization method I should bring forward then I will apply other techniques to reduce loss. I want to normalize every samples of train_set but I feel a problem e.g two original samples x_1, y_1 = [1,2,3,4], [5] and x_2, y_2 = [2,3,4,5], [6] after transformed -> [0,0.25,0.5,0.75], [1]. To overcome this I have tried `StandardScaler`, `RobustScaler` but they are the same except `MaxAbsScaler` but still `MinMaxScaler` produce better results. For conclusion I prefer MinMaxScaler since I think that sequentially values is very less chance in stock price data or never|
|06/28|2. normalize every samples with MinMaxScaler|1 1.125|||3.962|train_set from 2017-06-01 till 2017-12-31, mse score of 'A'|
|07/01|2.1 Increase date range of train_set from 2015 till end of 2017|[1.415, 10.238, 4.777, 1.445, 2.358]|||[4.043, 73.307, 25.308, 6.523, 13.365]|I want to compare 5 symbols (A, AAPL, ABAX, ACIU, ADUS) rather than only one symbol|
|07/01|2.2 Same amount of train_set but add one more feature 'volume'|[1.461, 9.537, 5.173, 1.469, 2.199]|||[4.227, 71.291, 24.006, 5.995, 16.004]|
|07/01|2.1.2 Apply moving average to input||||||