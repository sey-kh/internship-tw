# Stock price prediction with deep learning #

## 1. Project Overview ##

### 1.1 Introduction ###

In this project, you will see how you can use the recurrent neural network algorithm for forecasting, prediction and analysis of stock market data. As a stock buyer you can reasonably decide when to buy stocks and when to sell them to make a profit. So good machine learning models that can look at the history of a sequence of data and correctly predict what the future elements of the sequence are going to be can help you. In this project the model was trained on multiple companies data from <https://www.kaggle.com/ehallmar/daily-historical-stock-prices-1970-2018> and predicting future stock pricing.

### 1.2 Problem Statement ###

Stock market analysis is divided into two parts – Fundamental Analysis and Technical Analysis. Our focus will be on the technical analysis part by using statistical figures to identify the trends in the stock market.

* We aim to build a model that can generalize well enough to predict next days adjusted closing price of various stocks based on the dataset provided

* Construct model to predict adjusted closing price for 1, 3, 5, 10 days into the future

## 2. DEVELOPMENT ##

### 2.1 Data normalization ###

We do normalizing our stock price data into a range of (0,1) by using `MinMaxScaler(feature_range=(0,1))`. We're converting various values into a range (0,1) so that deep learning can visualize pattern of samples better.

Training set and Test set are being normalized every sample.

### 2.2 Deep learning model ###

To train our network model, GRU (Gated Recurrent Unit) is choosen. It kind of ilterate process by taking previous output to generate new output in terms of processing sequence data.

To assign the best network training parameters, the network model is put into the Hyper parameter optimization algorithm. The results does influence the way on how we finalize the fully connected layer of model.

### 2.3 Hyper parameters optimization ###

Hyper parameters optimization using Grid search to optimize the network model architecture parameters.

```py
n_neurons = [20, 30,32,60,64,80]
dropout_rate = [0.1, 0.2,0.3]
```

After performed Grid search algorithm we got result as below:

```py
print('Best Score: ', grid_result.best_score_)
print('Best Params: ', grid_result.best_params_)

Best Params:  {'dropout_rate': 0.3, 'n_neurons': 30}
```

## 3. EXPERIMENTATION, TESTING AND RESULTS ##

### 3.1 Prediction result of AAPL stock #

There are results of predicting adjusted closing price for 1, 3, 5, 10 days into the future

|                           |                           |
|---------------------------|---------------------------|
|![Screen Shot 2019-07-30 at 10 43 09 AM](https://user-images.githubusercontent.com/49018140/62109924-7f011180-b2d7-11e9-8be7-6fb8ea5170da.png)|![Screen Shot 2019-07-30 at 10 43 35 AM](https://user-images.githubusercontent.com/49018140/62109897-6ee93200-b2d7-11e9-9196-a5792f3234dc.png)|
|![Screen Shot 2019-07-30 at 10 43 48 AM](https://user-images.githubusercontent.com/49018140/62109866-609b1600-b2d7-11e9-90c3-1fb4dc4ede0a.png)|![Screen Shot 2019-07-30 at 10 44 00 AM](https://user-images.githubusercontent.com/49018140/62099069-17d36500-b2b7-11e9-8d3d-0fd34a3ba4f5.png)|

### 3.2 Model performance tracking ###

| Date  | Change                          | MSE Interval 1|MSE Interval 10| Description |Conslusion|
|-------|---------------------------------|---------------|---------------|-------------|----------|
|07/01|`Base line` train only one feature `adj_close`|(1.19, 0.86, 1.34, 2.68, 5.93)|(4.1, 3.34, 7.3, 17.53, 72.85)|I want to compare 5 symbols `(A, ACER, MSFT, ABC, AAPL)`||
|07/01|1 add one more feature `volume`|(1.22, 0.87, 1.27, 2.71, 6.58)|(4.0, 3.26, 7.34, 17.82, 57.78)|||
|07/02|1.1 Add `moving average of adj_close` instead of `volume`|(1.85, 4.08, 4.4, 7.33, 37.46)|(3.46, 5.13, 9.71, 19.77, 86.66)|||
|07/03|1.1.1 Add one more feature `volume`|(1.36, 1.74, 3.11, pri3.32, 23.66)|(4.14, 5.65, 6.86, 19.71, 70.42)||1 is similar to Base line but better than 1.1 and 1.1.1|

### 3.3 Conslusion #

Through out many testings on various stocks, I noted that it was able to predict well for next one day adjusted closing price of any symbols. As you can see as long as we increase interval days MSE error is getting bigger and model can not predict the market trends well.

## 4. PROBLEM AND CHALLENGES ##

Stock market prices are highly unpredictable and volatile. This means that there are no consistent patterns in the data that allow us to model stock prices over time near-perfectly.

## 5. DELIVERABLES ##

Although there are already multiples versions of experiment of the network models, the final evaluation should only be done as the result *base_line.ipynb* and *1_add_one_more_train_feature.ipynb* are similar and better than others.

The followings are the deliverables:

* GRU model training with performance tracking files
* Grid search optimization algorithm

_Deliverables are included in the github repository under /deliverables/ folder._
