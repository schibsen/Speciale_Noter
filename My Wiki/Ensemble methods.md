When we talk about ensemble method, we refer to the way how we fuse the information of different classifiers or regression methods. 

**Ensemble methods** refer to a broad class of machine learning techniques that combine multiple models to improve predictive performance . They include techniques like **bagging**, **boosting**, **stacking**, and more.

Some of the most common ones are listed below

# Averaging
- simple Averaging 
- weighted averaging 
- 

# Bagging
**bagging** is an ensemble method that involves training multiple base models on different subsets of the training data and then combining their predictions to make a final prediction. Some examples of ensemble models that use bagging include **Random Forest** and **Extra Trees**.

# Boosting
**Boosting** is an ensemble method that involves training multiple base models sequentially, with each model trying to correct the errors of the previous model. The final prediction is made by combining the predictions of all the models in the sequence. 
Some examples of ensemble models that use boosting include **AdaBoost**, **Gradient Boosting Machines (GBMs)**, and **LightGBM**
# Cascade
**cascading** is a specific type of ensemble method where the output of one model is used as input to the next model in a sequence. 
The models in the sequence can be of any type, including ensemble models like **LightGBM**

Ensemble learning based on the concatenation of several classifiers². 
In this method, the output from one classifier is used as additional information for the next classifier in the cascade.
- Unlike voting or stacking ensembles, which are multi-expert systems, cascading is a multistage process².
- Cascading classifiers are commonly used in image processing for object detection and tracking, particularly for facial detection and recognition.
- The first cascading classifier was developed by [[Viola-Jones object Detection|Paul Viola and Michael Jones in 2001 for face detection]]. The goal was to create a fast classifier that could be implemented on low-power CPUs, such as cameras and phones².

# Voting
In the ensemble voting method, a collection of diverse models, such as decision trees, naive Bayes, and support vector machines, are trained on the same dataset. Each model makes its own prediction, and the final prediction is made by aggregating the predictions of all the models. This can be done by selecting the class with the most votes (the statistical mode) or by combining the predicted probabilities.
# Stacking
**Stacking** is an ensemble method that combines the predictions of multiple machine learning models to make a final prediction. It involves training multiple base models on the same dataset and then using a meta-model to combine their predictions. The meta-model learns how to best combine the predictions of the base models³.

- The architecture of a stacking model typically involves two or more base models, often referred to as level-0 models, and a meta-model that combines their predictions, referred to as a level-1 model³.
- The base models are trained on the training data, and their predictions are compiled.
- The meta-model is then trained on the predictions made by the base models on out-of-sample data³.

- Stacking addresses the question: Given multiple machine learning models that are skillful on a problem but in different ways, how do you choose which model to use or trust? The approach is to use another machine learning model that learns when to use or trust each model in the ensemble³.




