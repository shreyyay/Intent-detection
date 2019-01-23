# Intent-detection

Intent detection using Enron email dataset. Intent here is correspond primarily to the categories "request" and "propose". The dataset contains parsed sentences from the email along with their intent (either 'yes' or 'no'). ou need to build a learning model which detects whether a given sentence has intent or not.

In this problem ELMO embedding is used as input to the model. The reson to use ELMO embedding is that it creates word vectors in the basis of context the word is used. ELMO embedding outperformed word2vec and glove in various NLP tasks.
As, there is no support for ELMO embedding in keras thus we have defined the ELMO_EMBEDDING function and use it using LAMBDA layer from keras.

We have converted the labels “YES” and “NO” to its corresponding numerical values using scikit learn preprocessing library.

In the model we have used 2 Dense layers, the last Dense layer is the output of the model with softmax as activation function. The reason to use softmax as activation function is tha label encoder from scikit learn encoded the labels as [0,1] and [1,0],  so we need two outputs from the model.

When we evaluate our model in the given test set we find 86.79% accuracy.

we can improve the accuracy of our model by concatenating ELMO embedding with diffrent word embedding like word2vec and glove.

Also we can use residual Bi-lstm connection in our model.

We can also add one or more convolution layer .
