# **Activation function** 

- The Activation Functions can be basically divided into 2 types:
  - Linear Activation Function
  - Non-linear Activation Functions

#### **_Linear Activation Function_**: 
- Equation: f(x) = x 
- It doesn’t help with the complexity parameters of usual data that is fed to the networks.


#### **_Non-linear Activation Function_**: 
1. **Sigmoid Function:**
  
  <img src="images/sigmoid_functions.png" width="500" height="300">

  - Range: (0, 1)
  - The larger the input (more positive), the closer the output value will be to 1.0
  - The function is differentiable --> can find the slope of the sigmoid curve at any two points.
  - The function is monotonic but function’s derivative is not
  

2. **Tanh Function:**
  
  <img src="images/tanh_func.jpeg" width="500" height="300">

  - Range: (-1, 1)
  - The advantage is that the negative inputs will be mapped strongly negative and the zero inputs will be mapped near zero in the tanh graph.

3. **ReLU Function:** improve th non-linear ability of the network and avoid the gradient disappearance or the gradient explosion after multiple iterations of network.
  
  <img src="images/ReLU_func.png" width="500" height="300">

  - Range: (0, infinity)
  - The function and its derivative both are monotonic.
  - ReLU family:

  <img src="images/prelu_formula.png" width="150" height="50">
  
      - Leaky ReLU: aᵢ > 0, f becomes leaky ReLU --> solve a dying ReLU problem
      - PReLU: aᵢ is a learnable parameter
  
 4. **Softmax Function:**

  <img src="images/softmax.png" width="150" height="50">
  
  - Range: (0, 1)
  - The softmax function is used as the activation function for multi-class classification problems where class membership is required on more than two class labels.
 
