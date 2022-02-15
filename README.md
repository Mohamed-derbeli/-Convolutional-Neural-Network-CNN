
# Regularization 

-Regularization help reduce Overfitting
-Regularization is a technique which makes slight modifications to the learning algorithm such that the model generalizes better. This in turn 
improves the model’s performance on the unseen data as well. Regularization penalizes the coefficients. it actually penalizes the weight matrices 
of the nodes.Regularization coefficient is so high -----> some of the weight matrices are nearly equal to zero----> result in a much simpler 
linear network and slight underfitting of the training data.

#  Regularization Techniques in Deep Learning: 
##L2 & L1 regularization: 

L1 and L2 are the most common types of regularization. These update the general cost function by adding another term known
                        # as the regularization term. ''Cost function = Loss (say, binary cross entropy) + Regularization term''
                        #Due to the addition of this regularization term, the values of weight matrices decrease because it assumes that a neural 
                        #network with smaller weight matrices leads to simpler models. Therefore, it will also reduce overfitting to quite an extent. 
## Dropout: 
At every iteration, it randomly selects some nodes and removes them along with all of their incoming and outgoing connections as shown below. 
## Data Augmentation: 
Data Augmentation The simplest way to reduce overfitting is to increase the size of the training data. In machine learning, we were not able to increase the size of training data as the labeled data was too costly. But, now let’s consider we are dealing with images. In this case, there are a few ways of increasing the size of the training data – rotating the image, flipping, scaling, shifting, etc. In the below image, some transformation has been done on the handwritten digits dataset. This technique is known as data augmentation. This usually provides a big leap in improving the accuracy of the model. It can be considered as a mandatory trick in order to improve our predictions. In keras, we can perform all of these transformations using ImageDataGenerator. It has a big list of arguments which you you can use to pre-process your training data. 

## Early stopping: 
Early stopping is a kind of cross-validation strategy where we keep one part of the training set as the validation set. When we see that the performance on the validation set is getting worse, we immediately stop the training on the model. This is known as early stopping. In keras, we can apply early stopping using the callbacks function. Below is the sample code for it.
 from keras.callbacks import EarlyStopping
 EarlyStopping(monitor='val_err', patience=5)
 Here, monitor denotes the quantity that needs to be monitored and ‘val_err’ denotes the validation error.
 Patience denotes the number of epochs with no further improvement after which the training will be stopped
