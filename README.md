# Fairness-aware-classification

## Project description
This project is about fairness-aware classification. Unfairness is measured in the datasets Adult (adult.csv), COMPAS (compass-scores.csv) and AdviceRobo (not publicly available). Four classifiers are used to determine the accuracy-fairness trade-off. The used techniques for unfairness prevention are Probabilistic Rejection, Fair Reweighing, Fair Preferential Sampling and Fair Relabeling which can all be found under their respective markdown cell. 
‘Toy example’, ‘Simulated data’, ‘German Credit’, ‘Communities and Crime’, ‘Bank Marketing’ were used as test datasets, but were not suitable for research and are therefore commented.

## How to use the project
If you wish to use a specific technique (with tuned hyperparameters) simply go to the respective markdown cell and comment out the dataset/classifier for which you wish to apply the technique on. Each function contains a docstring explaining the purpose of the function and its parameters/output. For some lines of code there exists some extra explanation as comment above the specific line.

## Explanation of most important markdown sections
- Import modules & define global variables: specify the path where to save all outputs here, for importing the datasets you have to manually change the code lines with ‘pd.read_csv(…)’
- Functions - Detect group fairness: functions which measure group fairness
- Functions - Train classifier: functions used to train a classifier with nested stratified k-fold cross-validation
- Functions - Show metrics: functions either printing or plotting the accuracy/fairness and the function ‘load_metrics’ which can load previously exported Excel files containing metrics
- Functions - Group unfairness prevention: functions which calculate the metrics necessary for the pre-processing techniques Fair Reweighing/Preferential Sampling
- Individual fairness: functions to optimize the weights for the weighted Podani’s distance function, functions to calculate the distance function of a dataset (using a weighted Podani’s distance function) function to determine m (threshold for when instances should be considered similar) and a function which returns the identified unfair instances (individual fairness for Adult is currently commented, but could be commented out if one wishes to use it)
- Plot accuracy-fairness trade-off: code to plot the fairness against the accuracy per dataset or per classifier (currently all commented, but could be commented out if one wishes to use it)
