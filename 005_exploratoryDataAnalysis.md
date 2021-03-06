## Exploratory Data Analysis

### 1. Exploratory Data Analysis (What/Why?)

* Better understand the data
* Generate hypotheses out of the data

### 2. Tools

* Visualization

Sometimes without modelling you can already find patterns within the data by using exploratory data analysis.

### 3. Steps

#### 3.1 Getting domain knowledge

* Understand the data, use google/wikipedia ask expert

#### 3.2. Check if the data is intuitive

* Check for outliers by looking at intuitive values

#### 3.3 How was the data generated? 

* Where features more weighted?
* Find out about the generation algorithm

### 4. Anonymized Data

Organizers are anonymizing data due to keep the information secret, but still make it useful for modelling.

* *Explore indiviual features:*
* Explore each feature and guess the column meaning
* Guess the column type
* Useful functions:

```
df.dtypes()
df.info()
x.value_counts()
x.isnull()
``` 
### 5. Visualization

5.1 To explore individual features:
* Histogram
Aggregate the data and but data into several different buckets.  
* Plots
* Statistics

5.2 To explore feature relations:

*Pairs:*
* Scatter Plot, Scatter Matrix
* Correlation plot

*Groups:*
* Corrplot + clustering
* Plot(index vs. feature statistics)

### 6. Dataset cleaning
* Remove constant features
* Remove features that do not occur on the test set
* Find duplicated features
```
for f in categorical_feats:
    traintest[f] = traintest[f].factorize()
traintest.T.drop_duplicates()
```


