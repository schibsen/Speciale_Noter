**ensemble models** are specific machine learning models that are designed to leverage the power of ensemble methods. These models are built by combining multiple base models, such as decision trees or neural networks, to create a more robust and accurate final model.

# Realizations of Bagging 
![[Ensemble methods#Bagging]]
## Random Forest: 
Random Forest is a popular ensemble model that combines multiple decision trees trained on different subsets of the training data.
## Extra-Trees:
Extra-Trees, also known as Extremely Randomized Trees, is another ensemble model that builds multiple decision trees with random splits and combines their predictions.
## Bagging Meta-Estimator: 
Bagging Meta-Estimator is a meta-estimator that can be used to turn any base estimator into a bagging ensemble model.

# Realizations of Boosting 
![[Ensemble methods#Boosting]]
## AdaBoost:
AdaBoost is one of the earliest and most popular boosting algorithms. It works by sequentially adding models that correct the residual prediction errors of the previous model.

## Gradient Boosting Machines (GBM):
GBM is a general term for boosting algorithms that use gradient descent optimization to minimize the loss function. Examples of GBM implementations include **XGBoost** and **LightGBM**

## Stochastic Gradient Boosting:
Stochastic Gradient Boosting, also known as Gradient Boosting with Randomness, introduces randomness into the training process to improve generalization and reduce overfitting.

# Realizations of Cascade
No specific realizations, rather a theoretical definition 
![[Ensemble methods#Cascade]]

# Realizations of Voting
![[Ensemble methods#Voting]]

## Voting Classifier (scikit-learn)
The Voting Classifier in scikit-learn is a powerful ensemble model that combines the predictions from multiple other models, such as decision trees, naive Bayes, and support vector machines.

## Weighted Majority Voting Ensemble 
This approach assigns different weights to each classifier in the ensemble based on their individual performances¹. 
Classifiers that correctly classify observations which are not correctly classified by most of the classifiers gain more weights in the ensemble¹.
The proposed method was compared with the Simple Majority Voting Ensemble approach in terms of classification accuracy on 28 benchmark datasets¹.
## Feature Weighted Linear Stacking (FWLS):
This Python framework allows you to build majority vote and feature weighted linear stacking (FWLS) ensemble models².
As an example, ensemble models are built to classify flower species of the Iris dataset using a support vector machine (SVM), random forest, and k-nearest neighbor².

## Bayesian Model Averaging (BMA)
**Bayesian Model Averaging (BMA)** is an ensemble model that improves predictive performance by combining predictions from multiple models in the space of considered candidate models¹. 

BMA casts model averaging into a Bayesian framework, providing a principled approach to combining models¹. 
It assigns weights to each model based on its posterior probability, reflecting the model's ability to explain the data¹.
BMA has been used in various domains, including statistical postprocessing of forecast ensembles from numerical weather prediction models³ and wind speed modeling⁴.

**Bayesian Model Averaging (BMA)** is an ensemble model that utilizes the Bayesian model averaging method. 
BMA combines predictions from multiple models by assigning weights to each model based on its posterior probability.
These weights reflect the model’s ability to explain the data, and they are used to make the final prediction. 
BMA has been used in various domains, including statistical postprocessing of forecast ensembles from numerical weather prediction models and wind speed modeling.
# Realizations of Stacking
![[Ensemble methods#Stacking]]
## Stacked Generalization:
Stacked Generalization, or stacking for short, is an ensemble machine learning algorithm that involves using a machine learning model to learn how to best combine the predictions from contributing ensemble members¹. It typically uses a diverse collection of model types, such as decision trees, naive Bayes, and support vector machines¹.

## Stacking Ensemble in scikit-learn:
The scikit-learn library provides a standard implementation of the stacking ensemble algorithm in Python⁵. It allows you to combine the predictions from multiple well-performing machine learning models to create a more accurate final prediction⁵.

