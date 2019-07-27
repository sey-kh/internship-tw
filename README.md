# 1. DEFINITION
## 1.1 Project Overview
## 1.2

# 2. DEVELOPMENT
## 2.1 Design Specification

# 3. EXPERIMENTATION, TESTING AND RESULTS
| Date  | Change                          | MSE 1|3|5|10| Description |Conslusion|
|-------|---------------------------------|----------------|-------------|----|----|----|----|
|07/01|`Base line` train only one feature `adj_close`|(1.19, 0.86, 1.34, 2.68, 5.93)|||(4.1, 3.34, 7.3, 17.53, 72.85)|I want to compare 5 symbols `(A, ACER, MSFT, ABC, AAPL)`||
|07/01|1 add one more feature `volume`|(1.22, 0.87, 1.27, 2.71, 6.58)|||(4.0, 3.26, 7.34, 17.82, 57.78)|||
|07/02|1.1 Add `moving average of adj_close` instead of `volume`|(1.85, 4.08, 4.4, 7.33, 37.46)|||(3.46, 5.13, 9.71, 19.77, 86.66)|||
|07/03|1.1.1 Add one more feature `volume`|(1.36, 1.74, 3.11, 3.32, 23.66)|||(4.14, 5.65, 6.86, 19.71, 70.42)||1 is similar to Base line but better than 1.1 and 1.1.1|