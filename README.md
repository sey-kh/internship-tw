# Model performance tracking
| Date  | Change                          | MSE 1|3|5|10| Description |Conslusion|
|-------|---------------------------------|----------------|-------------|----|----|----|----|
|07/01|`Base line` train only one feature `adj_close`|(1.64, 1.14, 3.93, 11.3, 18.89)|||(3.81, 5.16, 19.03, 84.17, 94.7)|I want to compare 5 symbols `(A, ACER, ABC, AAPL, BABA)`||
|07/01|1 add one more feature `volume`|(1.91, 1.26, 4.45, 9.85, 24.66)|||(3.88, 4.39, 20.43, 69.72, 93.18)|||
|07/02|1.1 Add `moving average of adj_close` instead of `volume`|(2.24, 3.03, 8.28, 23.63, 53.41)|||(3.52, 6.62, 20.97, 79.94, 142.98)|||
|07/03|1.1.1 Add one more feature `volume`|(1.53, 1.45, 4.1, 10.66, 19.64)|||(3.9, 5.99, 20.25, 69.35, 107.76)|||