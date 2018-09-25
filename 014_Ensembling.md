# Ensembling

## What is ensemble modeling?
* It means to combine many different ML models to get a better prediction

## Examined ensemble methods
1. Averaging (or blending)
2. Weighted averaging
3. Conditional averaging
4. Bagging
5. Boosting
6. Stacking
7. StackNet

### Averaging ensemble methods

```
(Model_1 + Model_2) / 2

or f.ex.:

(Model_1*0.7 + Model_2*0.3) / 2

```

### Bagging

* Means averaging slightly different versions of the same model to improve accuracy
* Why?
  * There are 2 sources of error
        1. Error due to Bias (underfitting)
        2. Error due to Variance (overfitting)
* Parameters that control bagging?
  * Changing the seed
  * Ros sampling or Bootstrapping
  * Shuffling
  * Columns sampling
  * Model specific parameters
  * Number of models (or bags)
  * (Optionally) parallelism
* Example: BaggingClassifier and Bagging Regressor from SkLearn

### Boosting
* Boosting is a form of weighted averaging of models, where each model is built sequentially via taking into account the past model performance.
* Main boosting types
  * Weighted based boosting
    * Error is calculated in absolute terms
    * Parameters: 
      * Learning rate (or shrinkage or eta)
      * Number of estimators
      * Input model - can be anything that accepts weights
    * Sub-boosting types
      * AdaBoost (sklearn)
      * LogitBoost (Weka)
  * Residual based boosting
    * Error becomes a new target variable
    * Parameters: 
      * Learning rate (or shrinkage or eta)
      * Number of estimators
      * Row sampling
      * Column sampling
      * Input model - better be trees
      * Sub-Boostring types:
        * Fully gradient based
        * Dart
      * Implementations: Xgboost, Lightgbm, H20's GBM, Catboost, Sklearn's GBM 

### Stacking
* Stacking is when making several predictions of a number of models in a hold-out set and then using a different (Meta) model to train on these predictions
* Methodology
  * Wolpert introduced stacking in 1992
    1. Splitting the train set into two disjoint sets
    2. Train several base learners on the first part
    3. Make predictions with the base learners on the second part
    4. Using the predictions from (3) as input to train a higher level learner
* Things to be mindful of
  * With time sensitive data - respect time
  * Diversity as important as performance. Can be controlled by,
    * choosing a different algorithm
    * different input features
  * Plateau after N models
  * Meta model is normally modest

### StackNet
* A scalable meta modeling methodology that utilizes stacking to combine multiple models in a neural network architecture of multiple levels
* Why would this be of any use?
  * You get better result with deep stacking
* StackNet as neural network
  * In a neural network, every node is a simple linear model
  * Instead of linear model we could use any model
* How to train?
  * We cannot use Backpropagation
  * We use stacking to link each model/node with target
  * To extend to many layers we use Kfold paradigm
  * No epochs


### Tips & Tricks
* 1st Level Tips
  * Diversity based on algorithm
    * 2-3 Gradient boosted trees
    * 2-3 Neural Nets
    * ^1-3 Extra Trees/Random Forest
    * 1-3 knn models
    * 1 Factorization machine
    * 1 SVM with nonlinear kernel if size/memory allows
* Diversity based on input data
  * Categorical features: label encoding
  * Numerical features: Outliers
  * Interactions: group by unsupervised
* Subsequent level tips
  * Simpler algorithms
    * GBM
    * Linear models
    * Extra Trees
    * Shallow networks
    * knn with BrayCurtis Distance
    * Brute force a search for best linear weights based on cv
  * Feature engineering
    * pairwise differences between meta features
    * Standard feature selection techniques
  * For every 7.5 models in previous level we ad 1 in meta
  * Be mindful of target leakage
* Software
  * StackNet 
  * Stacked ensembles from H2O
  * Xcessiv