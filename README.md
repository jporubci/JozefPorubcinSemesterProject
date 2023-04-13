# Neural Networks Semester Project
Author: Jozef Porubcin
Link to Google Colab: https://colab.research.google.com/drive/1WFEzGuNuRDETSa_2aoz_zdg7CnFynQ3Z?usp=sharing

# Report:

### Neural Network Architecture

This neural network is largely inspired from the convolutional neural network from Practical 2. As a result, it contains 5 convolutional layers and a hidden multilayer perceptron layer with two fully connected layers. ReLU was used as the loss function, max pooling was used for the 1st, 2nd, and 4th convolutional layers, batch normalization was used on the first two convolutional layers, and softmax was used for the last fully connected layer.

This architecture was chosen because it was successful for CIFAR 10, and since the data set for this project is a 14-class image classification, it is not much different, so a similar architecture should theoretically be good. A stochastic gradient descent optimizer is used with momentum, because I think momentum can help the model skip over small local minima, and potentially get closer to the glocal minimum.

### Evaluation Accuracy and Ideas for Future Improvement

The provided model achieves about a 70% accuracy when tested against training data, and slightly higher accuracy when training on validation data (the provided model scores an accuracy of about 35%, probably because I was working on removing pineberries from the dataset, and renaming black berry to blackberry, and I believe I may have accidentally messed something up in the process. Since the model takes too long to train however, I was unable to simply train a new model, so unfortunately I do not have a good model to show right now, however it was working previously).

The model was trained for 50 epochs, so it could be trained for more epochs. Furthermore, the number of images in the pineberry dataset is about half of the number of images in the rest of the fruit classes' sets, so removing the pineberry class would double the available training data. This is because the number of images of the fruit class with the fewest number of images is chosen as the number of images that will be used from each fruit class' dataset, so there is an equal number of images of each fruit from each class. This would make training the model take a lot longer, but more data would make its results more accurate (ideally).

Lastly, the entire purpose of this project is to test the model's ability to accurately classify fruits when the data contains noise, however noise has yet to be added to the project. I just wanted to get a working model first, then get noise to be added to the images. Lastly, a pre-trained network will be included so that the ability of the networks will be compared, and methods for improving resilience against noise in the data will be examined.
