# Use LSTM to predict the global active power
## Dataset: 
http://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption
## Choice of hyperparameters:
**Input_dim:** (the number of features) in the input data. In this instance, 
the number of features is provided by X train.shape[2]. <br>
**Hidden_dim:** (The amount of hidden units that are present in each 
LSTM layer) We settle on a number of 100 since it strikes a compromise 
between overfitting and model capability. <br>
**Num_layers:** (The number of LSTM layers in the model) I settle on 4 
because it's a typical value for medium- to large-scale sequence 
modelling projects and because it gives the model the capacity to 
capture long-term dependencies in the input sequence. <br>
**Output_dim:** ( the output feature count) which in this case is 1 as we 
are just forecasting a single value.
**Learning_rate:** 0.001 offers a fair trade-off between convergence speed 
and stability. <br>
**Batch_size:** I settle on 100 as our value since it strikes a compromise 
between model convergence and memory consumption. <br>
**Num_epochs:** In order to allow the model to converge to a decent 
solution without overfitting the training data, I chose a value of 45, 
which offers a respectable amount of iterations. <br>

## Results and Observations:
 Test loss with 80:20 train-test split= 0.0057 <br>
 Test loss with 70:30 train-test split= 0.0054 <br>

Since a larger test set comprises more different instances that the 
model has not encountered during training, it will typically give a more 
accurate approximation of the model's generalisation performance. <br>
If the test set is smaller and might not be sufficiently representative to 
accurately predict the model's performance on unobserved data when 
the train-test split is 70:30. Overfitting is a condition when a model 
performs well on training data but poorly on test data.<br>
The test set is bigger and contains more different instances that the 
model hasn't encountered during training when the train-test split is 
80:20, on the other hand. This can lessen the chance of overfitting and 
give a more accurate estimate of the model's generalisation ability
