# **Batch Normalization**


**1. Normalizing Input Data**
- When inputting data to a deep learning model, it is standard practice to normalize the data to zero mean and unit variance. --> features come in on similarity scale

    <img src="images/norm_data.png" width="150" height="250">
  - Features on different scales take longer to reach the minimum
  - Normalized data helps the network converge faster 
  - The loss function will on average look more symetric --> gradient descent can go straight to reach minimum


**2. Implementing Batch Norm**
- Batch Norm is a network layer that gets inserted between a hidden layer and the next hidden layer
  - Its job is to take the outputs from the first hidden layer and normalize them before passing them on as the input of the next hidden layer.
 
a. Training with Batch Norm Networks
  - Batch Norm layer has parameters:
    - Two learnable parameters called beta and gamma.
    - Two non-learnable parameters (Mean Moving Average and Variance Moving Average) 
  ![](images/batch-norm.png)
    
    - Activation: Applied to activation over a mini-batch
    - Caluculate Mean and Variance
    - Normalized: the normalisation that the inputs have mean = 0 and variance = 1
    - Scale and Shift: y = (gamma)* x_hat + (beta)
        - Batch Norm allows its values is shifted to a different mean) and scaled (to a different variance) --> by multiplying the normalized values by a factor, gamma, and adding to it a factor, beta (element-wise multiply)
        - These factors are not hyperparameters --> trainable parameters that are learned by the network
    - Moving Average: 
        - During training, Batch Norm calculates Exponential Moving Average (EMA). 
        - At the end of training, it simply saves this value as part of the layer’s state

b. Inference with Batch Norm Networks:
- With a single sample, in Batch Norm layer networks use mean and variance in Exponential Moving Average to normalize and apply that scale and shift for Inference.

**3. Advantages**
- Internal Covariate Shift: 
    - The problem of Covariate Shift — the model is fed data with a very different distribution than what it was previously trained with — even though that new data still conforms to the same target function --> spend more time re-learning --> slows down the training process
    - During training, each layer of the network learns an output function to fit its input. Each layer ends up trying to learn from a constantly shifting input, thus taking longer to converge and slowing down the training.
    - Batch Norm helps to stabilize these shifting distributions from one iteration to the next --> speeds up training

- Loss and Gradient Smoothening:
    - Batch Norm does to smoothen the loss landscape substantially by changing the distribution of the network’s weights. --> gradient descent can confidently take a step in a direction knowing that it will not find abrupt disruptions along the way --> take larger steps by using a bigger learning rate
