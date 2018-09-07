## Validation and Overfitting

### 1. Concept of Validation and Overfitting

In a nutshell validation is about proofing that a model can be applied to new data. Its about the model quality.

Overfitting in **"real world":** If the quality of the test set is worse than on the training set.
Overfitting in **"competition":** If the quality on the private test set is worse than on the training set.

### 2. Validation Types

#### 2.1 Hold Out

You divide data into two parts, basically you simply split the data. The model is trained on the training data.frame. Its a good choice if there is enough data.

`sklearn.model_selection.ShuffleSplit`

#### 2.2 K-Fold

Data is split into K-parts - folds - and the average is taken from each fold.

`sklearn.model_selection.Kfold`

#### 2.3 Leave one out

Data is left out and there are again several folds. The average is taken from each fold.

`sklearn.model_selection.LeaveOneOut`

### 3. Data splitting strategies

Different data splitting strategies can differ significantly...

1. in generated features
2. in a way the model will rely on that feature
3. in some kind of target leak

#### 3.1 Splitting Strategies

1. Random, rowwise
Rows are independent of each other. 

2. Timewise
Split on a certain date 
Special case for timewise split is a moving window validation

3. By id
Split on a certain id

4. Combined
Combine several above splits.

--> In Kaggle competition, match the same train/test split of the competition organizer

### 4. Validation Problems (during competition)

#### 4.1 Validation stage

Consider the following:
1. Too little data
2. Too diverse and inconsistant data

Extensive validation should be done here:
1. Average scores from different k-fold splits
2. Tune model on the splits, evaluate scores on the other


#### 4.2 Submission stage

1. LB score is consistently higher/lower that validations core
2. LB score is not correlated with validation score at all

