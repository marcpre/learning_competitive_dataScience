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
  