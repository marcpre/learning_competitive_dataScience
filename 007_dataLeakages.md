## Data Leakages

* What is it about?
It is unexpected information in the data that allows us to make unrealistically good predictions.

### 1. Basic Data Leakages

#### 1.1 Leakage types and examples

1. Leakes on time series
* Split should be based on time
* Even when split on time some features may contain information about the future (f.ex.: weather)

2. Unexpected Information
* For example images, meta data, information in IDs, row order
 

### 2. Leaderboard Probing

* Get "ground truths" from leaderboard to include in the data

### Example - Kaggle: Expedia Competition

* Expedia Competition was about predicting, which hotel to book.
* The var `destination_distance` gave a good approximation for the true hotel location