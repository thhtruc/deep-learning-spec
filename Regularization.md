# Regularization

### 1. Regularization:
- This is a technique which makes slight modifications to learning algorithms such that the model generalizes better --> avoid overfitting

a. L1&L2 regularization:
Adding another term as regularization: Cost function = Lost function + Regularization
  - L1 regularization: penalize the absolute value of weights 
  - L2 regularization: weight decay (it forces the wights to decay towards zero but not exactly zero)
    Cost function = Loss + lambda/2m * sum(norm_2 w)
    **lambda** is the regularization parameter (hyperparameter)

b. Dropout regularization:
  - At every iteration, it randomly selects some nodes and removes them along with all of their incoming and outgoing connections.

### 2. Data Augumentation:
- The simplest way to reduce overfitting is to increase the size of the training data such as rotating the image, flipping, scaling, shifting, ...
- Early Stopping: when the performance on validation set is getting worse, we immediately stop the training on the model
