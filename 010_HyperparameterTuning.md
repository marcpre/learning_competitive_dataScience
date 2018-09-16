## Hyperparameter Tuning

* How do we tune hyperparameters?
  1. Select the most influential parameters
  2. Understand how exactly they influence the training
  3. Tune them!
    * Manually (change and examine)
    * Automatically
* Libraries
  * Hyperot
  * etc.


## Tree based models
* GBDT
  * XGBoost:
    * max_depth
    * subsample
    * min_child_weight
    * eta, num_rounds
  * LightGBM: 
    * max_depth / num_leaves
    * bagging_fraction
    * min_data_in_leaf
    * learning_rate, num_iterations

## Neural Networks
* Libraries: Keras, Tensorflow, PyTorch
* Tune hyperparameters in networks: 
  * Increase number of neurons per layer
  * Number of layers
  * Optimizers: 
    * SGD + momentrum
    * Adam/Adadelta/Adagrad...
  * Batch size (try 32 or 64)
  * Learning rate
  

## Linear Models
* Libraries: Scikit-learn(SVC/SVR, LogisticRegression/SGDRegressor), Vowpal Wabbit (FTRL)
* Hyperparameter Tuning:
  * Regularization parameters (C, alpha, lambda, ...)