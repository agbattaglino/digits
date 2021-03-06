# digits

EDIT: Added a python adaptation using jupyter notebook (**numpy_nn.ipynb**)

**neuralNet.jl** contains my original implementation of a neural network training algorithm using the Julia programming language.  The user is able to specify any architecture as well as a regularization parameter, a learning rate, and the number of training epochs.  The data is first normalized by subtracting out the mean from each feature and dividing by the standard deviation.  I then use stochastic gradient descent to minimize the cross-entropy cost function with L2 regularization.  The optimal weights are returned along with the value of the cost function taken every 2000 steps of gradient descent.  The normalization is also returned as it is necessary for classifying new examples.  My classifier achieved a 97.0% accuracy in the Kaggle Digit Recognizer competition using two hidden layers of size 400 and 50.  For larger networks, computing time becomes prohibitive.

**CVneuralNet.jl** contains functions that let the user perform cross validation for the purpose of tuning hyperparameters.  One function performs k-fold cross validation whereas the other lets the user specify the size of the test set and makes only one pass.  Both return the value of the cost function on the test set(s) and the zero-one error rate.  K-fold cross validation is more robust, however it is slow as one neural network must be trained for each fold.  Vanilla cross validation is quicker, but can suffer high variance if one does not have much data.

Grab **exampleNN.csv** and run **exampleNN.jl** and try a toy example out for yourself!
