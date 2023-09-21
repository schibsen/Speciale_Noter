# Mean Squared Error (MSE):
This loss function is commonly used for regression problems. It calculates the average squared difference between predicted and actual values. The formula for MSE is:
$$MSE=\frac1{n}\sum_{i=1}^n​(y_i​-\hat{y}_i​)^2$$
Where:
- $n$ is the number of samples.
- $y_i$​ is the actual value.
- $\hat{y}_i$​ is the predicted value.
# Binary Cross-Entropy
This loss function is suitable for binary classification problems. It measures the dissimilarity between predicted probabilities and true labels. The formula for binary cross-entropy is:
$$BCE=-\frac1{n}\sum_{​i=1}^n  (​y_{i}​\log(\hat{y}_{​i} + (1-​y_{i})​\log(1-\hat{y}_{​i}))​$$
Where:
- $n$ is the number of samples.
- $y_i$​ is the true label (0 or 1).
- ​$\hat{y}_i$ is the predicted probability.
# Categorical Cross-Entropy
This loss function is used for multi-class classification problems. It quantifies the difference between predicted class probabilities and true labels. The formula for categorical cross-entropy is:
$$CCE=-\frac1{n}\sum_{​i=1}^n \sum_{​j=1}^m ​y_{ij}​\log(\hat{y}_{​ij})​$$
Where:
- $n$ is the number of samples.
- $m$ is the number of classes.
- $y_{ij}$​ is the true label (0 or 1) for sample $i$ and class $j$.
- $\hat{y}_{​ij​}$ is the predicted probability.
# Mean Absolute Error (MAE)
This loss function is commonly used for regression problems. It calculates the average absolute difference between predicted and actual values.
$$MSE=\frac1{n}\sum_{i=1}^n|y_i​-\hat{y}_i​|$$
Where:
- $n$ is the number of samples.
- $y_i$​ is the actual value.
- $\hat{y}_i$​ is the predicted value.
# Huber Loss:
This loss function is typically used in regression problems. It combines the best properties of mean absolute error and mean squared error, providing robustness to outliers.

$$MSE=\frac1{n}\sum_{i=1}^n​L_\delta(y_i​-\hat{y}_i​)$$
Where:
- $n$ is the number of samples.
- $y_i$​ is the actual value.
- $\hat{y}_i$​ is the predicted value.
- $L_\delta(y_i,\hat{y}_i)$ is defined as:
	- If $|y_i - \hat{y}_i|\leq\delta$, then $L_\delta(y_i,\hat{y}_i) = \frac12 (y_i​-\hat{y}_i​)^2$
	- If $|y_i - \hat{y}_i|>\delta$, then $L_\delta(y_i,\hat{y}_i) = \delta|y_i​-\hat{y}_i​|-\frac12\delta^2$
# Relative Entropy (Kullback-Leibler divergence):
This loss function measures the dissimilarity between two probability distributions. It is often used in generative models and information theory.   

$$KL(P\|Q)=\sum_i​ P(i)\log \left( \frac{Q(i)}{P(i)} \right)$$
Where:
- $P(i)$ and $Q(i)$ are the probabilities of events $i$ according to distributions $P$ and $Q$, respectively.
# Squared Hinge:
This loss function is commonly used in support vector machines (SVMs) for binary classification problems. It penalizes misclassifications and encourages a larger margin between classes.    
$$SHL=\frac1{n}\sum^n_{​i=1} \text{max}(0,1-y_i ​\hat{y}_​i​)^2$$

Where:
- $n$ is the number of samples.
- $y_i$​ is the true label ($-1$ or $1$).
- $\hat{y}_i$​ is the predicted score.
# Maximum Likelihood:
This loss function provides a framework for choosing an appropriate loss function when training neural networks and machine learning models in general


(https://www.theaidream.com/post/loss-functions-in-neural-networks)[1](https://www.theaidream.com/post/loss-functions-in-neural-networks).
    

These are just a few additional examples of loss functions used in neural network training. [Each loss function has its own properties and suitability for different problem types](https://www.theaidream.com/post/loss-functions-in-neural-networks)[1](https://www.theaidream.com/post/loss-functions-in-neural-networks). I hope this helps!

[](https://www.theaidream.com/post/loss-functions-in-neural-networks)[1](https://www.theaidream.com/post/loss-functions-in-neural-networks): [source](https://www.theaidream.com/post/loss-functions-in-neural-networks)