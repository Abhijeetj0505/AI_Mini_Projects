# AI projects
## Various projects based on Supervised and Unsupervised Deep Learning algorithms

This repo contains some of my AI projects. The structure of the Networks, such as the number of layers, the number of nodes in each layer,  the learning rate (where applicable) etc. were constructed in a simple way so the code can be used in simple systems too (Laptops without GPU etc.).
Furthemore, in the case of the Recommender Systems, I used some memory optimization so the program will use minimum computational power to execute.

**Note 1:** All of the projects, except the ANN one, can be subjected to parameter tuning through *Grid Search* and can be evaluated through *k-cross validation*. I did not apply these in all of the projects because of the computational power and time limitations. Nevertheless, the code-blueprint for executing the tuning and evaluation can be found in the *ANN project*. Feel free to copy and integrate it to the other projects too but keep in mind that it will require *a lot* of time in order to execute if your computational power is limited.

**Note 2:** You can also experiment with altering the actual structure of the Networks. Adding more layers, nodes and changing the activation functions can be simple but failry effective changes. In case you decide to implement the hyper-parameter tuning I suggest to play around with:  
            1. batch size\
            2. number of epochs\
            3. activation functions\
            4. different scoring methods
            
 I hope you find this repo useful and enjoy the **real life applications** they can support!
