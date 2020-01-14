"""""""""""""""""""""""""
Recurrent Neural Network
"""""""""""""""""""""""""

This problem is rather challenging since stocks follow a Brownian motion so the specific price cannot be predicted.
We can train the RNN though to predict an upward or downward future trend. To structure our RNN we used stacked Long Short-Term Memory
neural networks since LSTM networks are well-suited to classifying, processing and making predictions based on time series data.That is
because there can be lags of unknown duration between important events in a time series. They seem to have an outstanding performance when 
it comes to their applications in Deep Learning and they can effectively deal with the exploding and vanishing gradient problems that can 
be encountered when training traditional RNNs.

Some general info about the code and the functionality:

o	RNN is trained on 5 years of Google's stock price. Then based on correlations identified and captured by LSTM we predict 
	the first month of 2017.
o	The data contains the daily stock prices (20 days each month).
o	Created a data structure with 60 timesteps and 1 output. More specifically for every day the RNN refers to the 60 previous ones
	to train itself and predict the next day.
o	Created 2 datasers: X_train which contains for each day the 60 previous ones and Y_train which contains the price of the next day
	Implement this for every timestamp t, that is for every one of the days we have in our training dataset.
o	Created a RNN with 4 layers and introduced some Dropout Regularization in each one to avoid overfitting
