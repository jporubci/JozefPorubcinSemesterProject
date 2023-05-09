# Neural Networks Semester Project
Author: Jozef Porubcin

Link to Google Colab: https://colab.research.google.com/drive/1wFRrAmZO6DuUxexLTW4hSHNDk4qR7asq?usp=sharing

# Report:

### Testing data description

The size of the testing data subset is 1150. The size of the training data subset is 9195. The size of the validation data subset is 1149. The original dataset had far too many classifications to train a model on in a reasonable amount of time, so a subset of 14 of the classifications were chosen. The only metric for ruling out a given classification was its size. To train the model fairly, an equal number of samples from each classification are required, so the size of the subset of the dataset is equal to the product of the number of chosen classifications and the size of the classification with the fewest samples among the chosen classifications. I chose an arbitrary number of 14 for the number of classifications and I selected 14 classifications with high sample counts relative to the rest of the classifications in the dataset. After extracting a subset of the dataset, each classification had at least 821 samples. I believed it would be better to train for depth rather than breadth, so I valued classification sample sizes over the number of classifications when selecting the data. That said, I still wanted there to be numerous classifications to lower the chance that the model could randomly select a classification and be correct.

While 821 is a good number of samples per classification, I still would have liked to have had more so that the training data subset could be larger. Since I wanted a large training data subset, I chose to dedicate 80% of the data for training. The validation data and testing data subsets would be 10% each to make up the remainder of the data. The sizes of the latter two subsets are large enough to reliably determine the accuracy of the model on data it has never seen, but small enough to allow enough samples to be used for training. Given that the testing data subset had 1150 images total and the model accurately identified over 99% of them, I believe that the 80/10/10 split was ultimately sufficient in testing the model's ability to generalize its knowledge to correctly classify new data.

### Classification accuracy on test set

The exact classification accuracy varies based on the amount of noise in the data. The model is trained and validated on images with no noise, but the model can be tested on images with arbitrary amounts of noise. To be precise, the way noise is added to an image is as follows. Each pixel of an input image has a chance of being modified. If a pixel is randomly chosen to be modified, its RGB values will be replaced by random RGB values. The probability that pixels will be modified is chosen before the model receives the image, and is not modified until all of the pixels are evaluated. With a 0% chance, the most recent evaluation of the model achieved an accuracy of 99.65%. 

### Source Codes

The provided model achieved an accuracy of 99.65% on the test data with 200 epochs of training. This yielded a significant improvement over the ~70% accuracy from 50 epochs of training. 
