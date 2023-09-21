Optimizers are used to update the weights in a NN
# Gradient Descent (GD)
A fundamental optimization algorithm that adjusts the attributes of a neural network, such as weights and learning rate, to minimize losses.
- can be used with various loss functions. 
- It aims to minimize the loss by iteratively adjusting the model parameters in the direction of steepest descent.
# Stochastic Gradient Descent (SGD)
A variant of gradient descent that randomly selects a subset of training samples to compute the gradient, making it computationally efficient for large datasets.
-  loss functions that involve large dataset.
## deeper comments
**Stochastic Gradient Descent (SGD)** is an iterative optimization process used for optimizing machine learning models¹.
It is a variant of the Gradient Descent algorithm that addresses the computational inefficiency of traditional Gradient Descent methods when dealing with large datasets¹.

In SGD, instead of using the entire dataset for each iteration, only a single random training example (or a small batch) is selected to calculate the gradient and update the model parameters¹.
This random selection introduces randomness into the optimization process, hence the term "stochastic" in Stochastic Gradient Descent¹.

The advantage of using SGD is its computational efficiency, especially when dealing with large datasets¹.
By using a single example or a small batch, the computational cost per iteration is significantly reduced compared to traditional Gradient Descent methods that require processing the entire dataset¹.

Here's a high-level overview of the Stochastic Gradient Descent algorithm:

1. **Initialization**: Randomly initialize the parameters of the model.
2. **Set Parameters**: Determine the number of iterations and the learning rate (alpha) for updating the parameters.
3. **Stochastic Gradient Descent Loop**: Repeat the following steps until the model converges or reaches the maximum number of iterations:
    - Shuffle the training dataset to introduce randomness.
    - Iterate over each training example (or a small batch) in the shuffled order.
    - Compute the gradient of the cost function with respect to the model parameters using the current training example (or batch).
    - Update the model parameters by taking a step in the direction of the negative gradient, scaled by the learning rate.
    - Evaluate convergence criteria, such as the difference in the cost function between iterations of the gradient.
4. **Return Optimized Parameters**: Once the convergence criteria are met or the maximum number of iterations is reached, return the optimized model parameters¹.

# Mini-Batch Gradient Descent (MBGD)
A hybrid approach that combines the benefits of both GD and SGD by computing the gradient on a small batch of training samples.
# Momentum
An optimization algorithm that accelerates convergence by accumulating past gradients to determine the direction and speed of weight updates. 
# Adagrad (Adaptive Gradient Descent)
An algorithm that adapts the learning rate for each parameter based on its historical gradients, allowing for more significant updates for infrequent parameters.
# RMS Prop
A variant of Adagrad that addresses its diminishing learning rate problem by using an exponentially weighted moving average of squared gradients.
# ADAM
An adaptive learning rate optimization algorithm that combines the benefits of RMS Prop and momentum methods to achieve faster convergence.

These are just a few examples, and there are many other optimization algorithms used in neural networks. Each algorithm has its own strengths and weaknesses, making them suitable for different scenarios.

- It is widely used and performs well across different loss functions and architectures.

