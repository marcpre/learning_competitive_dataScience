## Metrics

* Metrics are used to evaluation our quality of our model.
* In a competition only the provided metric should be optimized for

### Regression Metrics

#### MSE, RMSE, R-Squared

*Mean Square Error*
* Basically measures the error that we have compared to the predictions
* Best constant: target value

*Root Mean Squared Error*
* It is similar to MSE as it minimizes the error

For example: Looking at absolut values of MSE/RMSE it is hard to predict if a model is good or not

*R-Squared*
* To calculate R2, MSE can be calculated

#### MAE (Mean Absolute Error)

* Usually used in finance
* Best constant: target median

*MAE vs MSE*
* Are there outliers in the data?
* -> Use MAE
* Are you sure they are outliers?
* -> Use MAE
* Or are they just unexpected values that we should still care about?
* -> Use MSE

#### (R)MSPE, MAPE

*(Relative) Mean Squared Prediction Error*
* Basically uses the relative error instead of the absoute
* Weigthed version of MSE
* Best constant: weigthed target mean

*Mean absolute percentage error*

#### (R)MSLE - Root Mean Squared Logarithmic error
* Does not differ much from MSE
* Its basically MSE in log space

 
### Classification Metrics

#### Accuracy
* This value describes, how frequent our prediction is correct
* Best constant: 
  * predict the most frequent class

#### Area under ROC curve
* Only for binary tasks
* Depends only on ordering of the predictions, not on absolute values
* We plot the points on a matrix - false/true positives. Then we calculate the area under the curve. 
* Best constant:
  * All constant give same score

#### (Quadratic weighted) Kappa/Cohens Kappa
* For an accuracy of 1 we get 1 and for a baseline we get 0
* Similar to R^2

### General approaches to metric optimization
* Target metric is what we want to optimized
* Loss function is, what the model is using to optimize itself
* Approaches for target metric optimization
  * Some metrics can be optimized directly(MSE, Logloss)
  * Preprocess train and optimize another metricOptimize another metric
  * Write custom loss function

## Metric Optimization for Regression Metrics

### RMSE, MSE, R-Squared
* Just find the right model for optimization
* Libraries:
  * Tree-based: XGBoost, LightGBM
  * Linear-based: sklearn.<>Regression, sklearn.SGDRegression, Vowpal Wabbit (quantil loss)
  * Neural Nets: Pytorch, Keras, TF, etc.

### MAE
* Libraries:
  * Tree-based: LightGBM
  * Linear-based: Vowpal Wabbit (quantil loss)
  * Neural Nets: Pytorch, Keras, TF, etc.

### MSPE and MAPE
* Optimize as weighted MSE
* Not every library accepts sample weights
  * XGBoost, LightGBM accept
  * Neural Nets
    * Easy to implement if not supported
* Resample the train set

### RMSLE
* Transform target and fit a model with MSE loss  
  
  



