""""""""""""""""""""""""""
Artificial Neural Network
""""""""""""""""""""""""""

In this problem we utilize the Artificial Neural Network to solve a customer churn problem of a bank. We Used a sample of 10,000 customers
of a bank and their personal credit data to create a demographic centric model which predicts which of the customers are at highest risk of
leaving the bank. The data is fictional since datasets containing this kind of information is prohibited for public usage. In order to obtain
this data we monitored these customers for the past 6 months and saw whether they exited or not (1 or 0). It should be noted that even though
we chose to use this data in this specific manner we could use the very same data for checking either things like is customer should get a
loan or not should the person be approved for credit or not. 


Some general info about the structure and the functionality of the ANN:

o	Created 1 input layer 2 hidden layers and 1 output layer. Used rectifier activation functio for first two, 
	and sigmoid for hidden to output. 
o	The input layer has 11 nodes ad the hidden layers have 6 nodes each. The output layer has obviously only1 node.
o	We evaluate our model through 10-fold cross validation. 
o	For improving the model we could add some Dropout Regularization but the results do not show any overfitting.
o	Tuned our hyperparameters with Grid Search. Anyone using the code can try different values as tuning parameters. 
o	I chose to tune the batch seize, the number of epocks and the optimizer but that is subset to personal preference.
