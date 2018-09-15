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