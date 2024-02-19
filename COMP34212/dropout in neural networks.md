[[COMP34212]]
[towards data science](https://towardsdatascience.com/dropout-in-neural-networks-47a162d621d9)

- dropout is a method used to prevent [[overfitting and underfitting|overfitting]] within a neural network

> dropout refers to each neuron/node in the network becoming 'dropped' i.e. inactive with some random probability during each training minibatch - all the forward/backward weights associated with the neuron are ignored

- the associated hyperparameter with dropout is the probability of which you drop the nodes
- this forces the network to become accurate even in the absence of certain information/neurons

![](https://i.imgur.com/tvJ8DSv.png)
