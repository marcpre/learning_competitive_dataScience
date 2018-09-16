## Tips & Tricks

## Before you enter a competiton
* Define your goals. What can you get out of the competition?(tools, metal, learn more about interesting problems etc.)

## Working with ideas
* Organize ideas 
* Select the most important and promising ideas
* Try to understand WHY something works

## Everything is a hyperparameter
* Sort all parameters by these principles:
  * Importance
  * Feasibility
  * Understanding

## Data Loading
* Do basic data preprocessing from csv/txt to hdf5/npy for much faster loading
* Do not forget the data is stored in 64-bits, you can safe time when downsizing to 32-bits
* Process large data in chunks

## Performance evaulation
* Start with fastest models - LightGBM

## Fast and dirty always better
* Keep things simply

## Initial pipeline
* Start with a simple/primitive solution
* Debug full pipeline
  * From reading data to writing submission file
* From simple to complex (Start f.ex.: Random Forest)
* Start with an EDA and a baseline
* Add features in bulk -> generate as many as possible
* Always use git and use a seperate notebook for every transmission
* Use macros in jupyter