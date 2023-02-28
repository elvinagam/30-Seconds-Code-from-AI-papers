Distilling the Knowledge in a Neural Network

Authors are describing how to best 'distill' the knowledge of a large network (or an ensemble of networks - anytime I refer to a large network in this example,
it could also refer to an ensemble of network) into a single smaller neural network. 
The idea is to train a smaller network that, given an input, will produce the same output that the larger network would produce given the same input. 
To do this, they need to specify how they would like to train the smaller network to appropriately match the larger model. 
For a classification task, the desired output of a model is a label representing the 'class' the input belongs to. 
In the MNIST dataset the authors refer to in the paper, there are 10 possible classes (0-9). 
Therefore, you can think of the output of the classification task as a binary vector with nine 0s and one 1. 
The index of the 1 is the class label. 
To ensure that the smaller neural network provides the same output as the larger network one could use a cost function that forces the small network to always try and produce the same class label as the larger network. 
This approach is what Hinton et. al would refer to as matching the hard targets. 
However, as they mention in the paper, you are actually losing a lot of information that exists in the larger network when you train the smaller network in such a fashion. 
What information? Well, in classification tasks, people often use a softmax function as the last layer of their neural network which outputs a vector of class probabilities. 
So for the MNIST dataset, each input would produce a output vector of 10 probabilities, which not only tells you the most likely class, but also gives you information about the relative likelihood of each other class. 
Therefore, another way you could train the smaller network to match the larger network would be to use a cost function that tries to match each class probability in the output. 
The class probabilities are what Hinton et. al are referring to as the soft targets.
