# Model performance tracking
| Date  | Change                          | MSE 1|3|5|10| Description |Conslusion|
|-------|---------------------------------|----------------|-------------|----|----|----|----|
|07/01|`Base line` train only one feature `adj_close`|(1.8, 1.32, 2.22, 4.43, 13.07)|||(4.03, 5.3, 9.26, 20.13, 75.52)|I want to compare 5 symbols `(A, ACER, MSFT, ABC, AAPL)`||
|07/01|1 add one more feature `volume`|(1.44, 1.21, 1.77, 3.39, 8.94)|||(4.19, 4.61, 9.07, 20.89, 74.04)|||
|07/02|1.1 Add `moving average of adj_close` instead of `volume`|(2.18, 2.84, 2.47, 7.35, 22.25)|||(3.34, 6.11, 9.11, 20.32, 80.52)|||
|07/03|1.1.1 Add one more feature `volume`|(2.2, 2.06, 2.31, 5.47, 14.67)|||(3.92, 6.77, 7.1, 19.55, 70.43)|||