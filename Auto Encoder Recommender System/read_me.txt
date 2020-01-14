"""""""""""""""""""""""""""""""""
Auto Encoders Recommender System
"""""""""""""""""""""""""""""""""

This is a recommender system built based on the theory of "Stacked Auto Encoders". This system is built from scratch, the layers,
the nodes and the functionality are manually coded. For the training of our SAE we use 100,000 ratings, but in the "data" folder 
a set with 1,000,000 ratings is also provides in case someone wants to achieve better results. Compared to the RBM Recommender system,
this one also achieves powerful results but with a much simpler structure. The purpose is to predict a star-based (1-5) rating from
the user based on his past ratings. 

Some general info about the code and the functionality:

o	Using pytorch to build them from scratch and converting the data into Torch tensors
o	Creating the architecture of the Neural Network: 
	-Input layer to encoding layer with 20 nodes 
	-Encoding with 20 nodes to Encoding with 10 nodes
	-Encoding with 10 nodes to Encoding with 20 nodes  
	-Encoding with 20 nodes to the output layer
o	Create a function for forward probagation that will do the encoding and decoding and apply the different activation 
	functions insidei the full connections. Returns the vector of predicted ratings that will be compared with the vector of the real ratings. 
o	Used optimizer RMSprop (root mean squared)

