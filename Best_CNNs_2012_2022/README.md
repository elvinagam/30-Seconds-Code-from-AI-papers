Well-know CNN architectures and how they evolved through years

Since 2012 to today's 2022, there have been a huge leap forward in terms of ImageNet accuracy metrics. A hard jump from ~60% accuracy to over 90% now. 


Few terminologies in CNNs:
Wider network - More feature maps or more filters in convolutional layers (filter is multiplying matrice/template which helps to find pattern in convolved input)
Deeper network - More convolutional layers

AlexNet - 5 convolutional + 3 fully connected layers
Used Relu instead of Tanh to add non-linearity. It accelerates the speed by 6 times at the same accuracy.
Use dropout instead of regularisation to deal with overfitting. However the training time is doubled with the dropout rate of 0.5. (Dropout roughly doubles the number of iterations required to converge. However, training time for each epoch is less.)
Overlap pooling to reduce the size of network.
