# Fairness-aware-classification

## Project description
In this project the fairness in datasets is measured. In addition unfairness prevention techniques are applied for different classifiers after which the accuracy and fairness of the respective classifier is measured.
- Datasets: Adult (adult.csv), COMPAS (compass-scores.csv) and AdviceRobo (not publicly available)
- Datasets not suitable for research: Toy example, Simulated data, German Credit, Communities and Crime, Bank Marketing
- Notions of fairness: conditional demographic parity (get_d_unfair()), individual fairness (get_unfair_instances())
- Classifiers: naïve bayes, k-nearest neighbors, decision tree, logistic regression
- Unfairness prevention techniques: Probabilistic Rejection, Fair Reweighing, Fair Preferential Sampling, Fair Relabeling (each technique can be found under its respective markdown cell)

## Structure of Jupyter Notebook file
```
├── Import modules & define global variables
├── Functions
│   ├── Data cleaning
│   ├── Data exploration
│   ├── Detect group unfairness
│   ├── Train classifier
│   ├── Show metrics
│   └── Group unfairness prevention
├── Load datasets + define sensitive/explanatory attributes
│   ├── Toy example
│   ├── Simulated data
│   ├── German Credit
│   ├── Adult
│   ├── Communities and Crime
│   ├── Bank Marketing
│   ├── COMPAS
│   ├── AdviceRobo
│   │   ├── Try age as sensitive attribute
│   │   └── Continue with language as sensitive attribute
├── Individual fairness
│   ├── Optimize weights functions
│   ├── Detect unfair instances functions
│   └── Get weights, d_matrix, m for all datasets
├── Probabilistic Rejection
├── Fair Reweighing
├── Fair Preferential Sampling
├── Fair Relabeling
├── Plot accuracy-fairness trade-off
│   ├── Plot different classifiers for same dataset
│   ├── Plot same classifier for different datasets
│   └── Plot same classifier/dataset for D_u & U
```

## Explanation of most important markdown sections
- Import modules & define global variables: specify the path where to save all outputs here, to import datasets you have to manually change the code lines with ‘pd.read_csv(…)’
- Functions - Detect group fairness: functions which measure group fairness
- Functions - Train classifier: functions used to train a classifier with nested stratified k-fold cross-validation
- Functions - Show metrics: functions either printing or plotting the accuracy/fairness and the function ‘load_metrics’ which can load previously exported Excel files containing metrics
- Functions - Group unfairness prevention: functions which calculate the metrics necessary for the pre-processing techniques Fair Reweighing/Preferential Sampling
- Individual fairness: functions to optimize the weights for the weighted Podani’s distance function, functions to calculate the distance function of a dataset (using a weighted Podani’s distance function), function to determine m (threshold for when instances should be considered similar) and a function which returns the identified unfair instances (individual fairness for Adult is currently commented, but could be commented out if one wishes to use it)
- Plot accuracy-fairness trade-off: code to plot the fairness against the accuracy per dataset or per classifier (currently all commented, but could be commented out if one wishes to use it)

## How to use the project
If you wish to use a specific technique (with tuned hyperparameters) simply go to the respective markdown cell and comment out the classifier/dataset for which you wish to apply the technique on. Each function contains a docstring explaining the purpose of the function and its parameters/output. For some lines of code there exists some extra explanation as comment above the specific line.
