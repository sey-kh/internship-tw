# Model performance tracking
<<<<<<< HEAD

| Date  | Change                          | MSE (test set) | Description |
|-------|---------------------------------|----------------|-------------|
|06/26|Normalize each symbols|val_loss:[0.0007, 0.0017, 0.0027, 0.0050] interval 1,3,5,10 respectively to val_loss|This result preduced by train_set from 2015 till end of 2017|
|06/27  |Same amount of train_set but normalize every samples|val_loss:[0.0119, 0.329, 0.0220, 0.0396] interval 1,3,5,10 respectively to val_loss|This mse value can not compare to mse value of previous model where we nomalize data in different way. Once we do normalizing every samples then evey single elements is higher value than normalize each symbols. So the only way to compare the performance is comparing loss value on test set, please refer to my notebook updated on 06/27|
=======
>>>>>>> 73d73e999fc5366c3e6f7a92af98cc260542fe77
