## Kazanova's Competition pipeline

### Pipeline
1. Understanding the problem (1 day)
  * Type of problem
  * How BIG is the data?
  * Hardware needed (CPU, RAM, Disk space)
  * Software needed (TF, sklearn, Lightgbm, xgboost)
  * What is the metric tested on?
2. Exploratory analysis (1-2 days)
  * Plot histograms of variables
  * Check for features between train and test set
  * Consider univariate predictability metrics (IV,R,auc)
  * Binning numerical features and correlation matrices
2.1 Define cross-validation strategy
  * Is time important? -> Time-based validation
  * Are there different entities? -> Stratigied validation
  * Is the train/test data completly random? -> random validation (random K-fold)
  * Combination of all the above
  * Use test leaderboard to test
2.2 Feature engineering (3-4 days)
2.3 Modeling (until 3-4 days)
  * 
3. Ensembling (last 3-4 days)