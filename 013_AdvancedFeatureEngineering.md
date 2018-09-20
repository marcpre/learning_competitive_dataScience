# Advanced Feature Engineering

## Group By
* Example.: Ad sets

## Nearest Neighborhood Methods
* Example: Number of houses, Average price per square meter
  * Aggregate neighborhoods based on data

## Matrix Factorization
* What is it?
  * Create a matrix of two features and count occurances
* Restrictions:
  * Can be applied only for some columns
  * Can provide additional diversity
  * It is a lossy transformation, we loose information after some reduction
* Example implementations: sklearn, svd and pca, truncatedSVD

## Feature Interactions
* Construct a feature out of two other features
* You can use:
  * multiplication
  * sum
  * diff
  * division
* N^2 features can be build
* Random forest can be used to select most important features
* You can also use the leafs of a tree based model, see:
  * tree_model.apply()
  * booster.predict(pred_leaf=True)

## tSNE
* Is used in exploratory data analysis
* You can get new features from data
* sklearn can be found an implementation

