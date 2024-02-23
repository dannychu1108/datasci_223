## By Danny Chu, Hyelee Kim, and Morgan O'Connor

## Classify all symbols 
Here, the outcome is the categorical variables without orders (a total of 62 outcomes). 
Therefore, we need to generate a model that predicts different values using the image data.
Given that the neural network can better predict the outcome of image data than other models, we chose a neural network. 
Therefore, the loss function was set as a categorical cross entropy. In the fitting model, the epochs were 10, and the batch size was 200.
We could see that in the training model, the accuracy has increased per every epoch, but in the validation set, the accuracy was around 0.84.

In the subset of letters, we repeated the model where the outcomes are only letters (a total of 52 outcomes).
Then, the model accuracy improved to around 0.91, even in the validation set.

Likewise, in the subset of digits, the model accuracy has improved around 0.99 (after rounding) in the validation set. 

To improve the model performance, we increased the epochs from 10 to 15 in the digit-prediction model. 
In each epoch, the accuracy of the validation set remained between 0.9901 and 0.9909, indicating the increased accuracy 
compared to the epoch of 10.

## Classify digits vs. letter model showdown
The evaluation metric I used here is accuracy. The new label of 0, 1 was created based on whether the outcome is a digit or a letter. 

The models I chose were Ridge regression, k-nearest neighbour, gradient boosring and random forest. 

Hyperparameters were chosen to speed up the code running progress, so they were not picked to have a better model. It was trained with the best hyperparameter with 3-fold validation. Then the training was done using the parameter on the whole training data (together with test dataset).

The validation set (named as test here) was taken from the emnist package, and the first 1000 data rows to train in order to speed up the training process and the 429 data rows as test data (named as validation). The mean score of 3-fold test accuracy was used as the "final model" to test on validation data. 
