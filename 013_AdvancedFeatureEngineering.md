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