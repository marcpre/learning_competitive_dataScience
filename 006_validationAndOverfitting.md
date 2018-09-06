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
