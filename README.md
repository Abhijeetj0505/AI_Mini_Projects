# AI mini projects
## Various projects based on Supervised and Unsupervised Deep Learning algorithms

This repo contains some of my AI projects. The structure of the Networks, such as the number of layers, the number of nodes in each layer,  the learning rate (where applicable) etc. were constructed in a simple way so the code can be used in simple systems too (Laptops without GPU).
Furthemore, in the case of the Recommender Systems, I used some memory optimization so the program will use minimum computational power to execute.

**Note 1:** All of the projects, except the ANN one, can be subjected to parameter tuning through *Grid Search* and can be evaluated through *k-cross validation*. I did not apply these in all of the projects because of the computational power and time limitations. Nevertheless, the code-blueprint for executing the tuning and evaluation can be found in the *ANN project*. Feel free to copy and integrate it to the other projects too but keep in mind that it will require *a lot* of time in order to execute if your computational power is limited.

**Note 2:** You can also experiment with altering the actual structure of the Networks. Adding more layers, nodes and changing the activation functions can be simple but failry effective changes. In case you decide to implement the hyper-parameter tuning I suggest to play around with:  
            1. batch size\
            2. number of epochs\
            3. activation functions\
            4. different scoring methods
            
 ### Project 1 - Artificial Neural Network

In this problem we utilize the Artificial Neural Network to solve a customer churn problem of a bank. We Used a sample of 10,000 customers of a bank and their personal credit data to create a demographic centric model which predicts which of the customers are at highest risk of leaving the bank. The data is fictional since datasets containing this kind of information is prohibited for public usage. In order to obtain this data we monitored these customers for the past 6 months and saw whether they exited or not (1 or 0). It should be noted that even though we chose to use this data in this specific manner we could use the very same data for checking either things like is customer should get a loan or not should the person be approved for credit or not. 

Some general info about the structure and the functionality of the ANN:

-	Created 1 input layer 2 hidden layers and 1 output layer. Used rectifier activation functio for first two, 
	and sigmoid for hidden to output. 
-	The input layer has 11 nodes ad the hidden layers have 6 nodes each. The output layer has obviously only1 node.
-	We evaluate our model through 10-fold cross validation. 
-	For improving the model we could add some Dropout Regularization but the results do not show any overfitting.
-	Tuned our hyperparameters with Grid Search. Anyone using the code can try different values as tuning parameters. 
-	I chose to tune the batch seize, the number of epocks and the optimizer but that is subset to personal preference.

 ### Project 2 - Auto Encoders Recommender System

This is a recommender system built based on the theory of "Stacked Auto Encoders". The system is built from scratch, the layers,
the nodes and the functionality are manually coded. For the training of our SAE we use 100,000 ratings, but in the "data" folder 
a set with 1,000,000 ratings is also provides in case someone wants to achieve better results. Compared to the RBM Recommender system,
this one also achieves powerful results but with a much simpler structure. The purpose is to predict a star-based (1-5) rating from
the user based on his past ratings. 

Some general info about the code and the functionality:

* Using pytorch to build them from scratch and converting the data into Torch tensors
* Creating the architecture of the Neural Network:

            1)Input layer to encoding layer with 20 nodes 
            2)Encoding with 20 nodes to Encoding with 10 nodes
            3)Encoding with 10 nodes to Encoding with 20 nodes  
            4)Encoding with 20 nodes to the output layer
* Create a function for forward probagation that will do the encoding and decoding and apply the different activation 
functions insidei the full connections. Returns the vector of predicted ratings that will be compared with the vector of the real ratings. 
* Used optimizer RMSprop (root mean squared)


### Project 3 - Boltzmann Machine Recommender System

This is a recommender system built based on the theory of "Restricted Boltzmann Machines". This system is built from scratch, the layers,the nodes and the functionality are manually coded. There are available libraries which someone can use to replicate a RBM though. For the training of our RBM we use 100,000 ratings, but in the "data" folder a set with 1,000,000 ratings is also provides in case someone wants to achieve better results. 

Some general info about the code and the functionality:

*	Predicts a binary outcome, if the customer will like (yes or no) the product (movie)
*	Used dataset MovieLens with 100,000 ratings and 1,700 movies
*	Restricted Boltzmann Machine (RBM) from scratch based on the paper posted as a PDF
*	Contains a class which applies the k-step contrastive divergence technique in order to approximate and maximize likelihood 
*	Used gibbs sampling to estimate the gradience of the likelihood. 
*	Inputs: ratings of the movies by the different users, users are the observations who are fed in the rbm one by one
*	Users are put as the lines and movies as the columns
*	Converted the data into torch sensors
*	Converted the ratings (0-5) into binary ratings 1 (Liked) or 0 (Not Liked)
*	Calculate the weights and update them between each pass from hidden to visible nodes and back
 
 
 
 
 
### Project 4 - Recurrent Neural Network
This problem is rather challenging since stocks follow a Brownian motion so the specific price cannot be predicted.
We can train the RNN though to predict an upward or downward future trend. To structure our RNN we used stacked Long Short-Term Memory
neural networks since LSTM networks are well-suited to classifying, processing and making predictions based on time series data.That is
because there can be lags of unknown duration between important events in a time series. They seem to have an outstanding performance when it comes to their applications in Deep Learning and they can effectively deal with the exploding and vanishing gradient problems that can be encountered when training traditional RNNs.

Some general info about the code and the functionality:

*	RNN is trained on 5 years of Google's stock price. Then based on correlations identified and captured by LSTM we predict 
	the first month of 2017.
*	The data contains the daily stock prices (20 days each month).
*	Created a data structure with 60 timesteps and 1 output. More specifically for every day the RNN refers to the 60 previous ones
	to train itself and predict the next day.
*	Created 2 datasers: X_train which contains for each day the 60 previous ones and Y_train which contains the price of the next day
	Implement this for every timestamp t, that is for every one of the days we have in our training dataset.
*	Created a RNN with 4 layers and introduced some Dropout Regularization in each one to avoid overfitting

I hope you find this repo useful and enjoy the **real life applications** they can support!
