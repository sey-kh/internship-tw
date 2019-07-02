# Model performance tracking
| Date  | Change                          | MSE Interval 1|Interval 3|Interval 5|Interval 10| Description |Conslusion|
|-------|---------------------------------|----------------|-------------|----|----|----|----|
|06/28|Base line|1.142|||5.587|normalize each symbols with MinMaxScaler, train_set from 2017-06-01 till 2017-12-31, mse score of 'A'||
|06/28|1. keras normalization experiment|||||I want to finalize which normalization method I should bring forward then I will apply other techniques to reduce loss. I want to normalize every samples of train_set but I feel a problem e.g two original samples x_1, y_1 = [1,2,3,4], [5] and x_2, y_2 = [2,3,4,5], [6] after transformed -> [0,0.25,0.5,0.75], [1]. To overcome this I have tried `StandardScaler`, `RobustScaler` but they are the same except `MaxAbsScaler` but still `MinMaxScaler` produce better results. For conclusion I prefer MinMaxScaler since I think that sequentially values is very less chance in stock price data or never|I'm going to take MinMaxScaler and normalize+|
|06/28|2. normalize every samples with MinMaxScaler|1 1.125|||3.962|train_set from 2017-06-01 till 2017-12-31, mse score of 'A'||
|07/01|2.1 Increase date range of train_set from 2015 till end of 2017 but only 100 symbols and train only one feature 'adj_close'|[1.535, 12.889, 5.943, 1.468, 2.615]|||[4.079, 76.03, 30.642, 6.361, 16.171]|I want to compare 5 symbols (A, AAPL, ABAX, ACIU, ADUS) rather than only one symbol||
|07/01|2.1.1 Same amount of train_set but add one more feature 'volume'|[1.379, 9.487, 4.49, 1.374, 2.807]|||[4.119, 72.137, 23.592, 5.834, 16.364]|||
|07/02|2.1.2 Add new feature 'moving average of adj_close' instead of 'volume'|[1.962, 22.62, 14.94, 2.598, 5.116]|||[3.45, 67.873, 29.277, 7.823, 17.222]





|||