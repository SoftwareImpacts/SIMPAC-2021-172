# MrSQM: Fast Feature Selection for Time Series Classification with Symbolic Representations

MrSQM (Multiple Representations Sequence Miner) is time series classifier. The 
MrSQM method can quickly extract features from multiple symbolic representations of time series and train a linear classification model with logistic regression. The method has four variants with four different feature selection strategies:

  * MrSQM-R: Random feature selection.
  * MrSQM-RS: MrSQM-R with a follow-up Chi2 test to filter less important features.
  * MrSQM-S: Pruning the all-subsequence feature space with a Chi2 bound and selecting the optimal set of top *k* subsequences.
  * MrSQM-SR: Random sampling of the features from the output of MrSQM-S.

## Installation

Dependencies
```
cython >= 0.29
numpy >= 1.18
pandas >= 1.0.3
scikit-learn >= 0.22
fftw3 (http://www.fftw.org/)
```

Download the repository: 
```
git clone https://github.com/mlgig/mrsqm.git
```
Move into the code directory of the repository: 
```
cd mrsqm/mrsqm
```
Build package from source using: 
```
pip install .
```
## Example

Load data from arff files
```
X_train,y_train = util.load_from_arff_to_dataframe("data/Coffee/Coffee_TRAIN.arff")
X_test,y_test = util.load_from_arff_to_dataframe("data/Coffee/Coffee_TEST.arff")
```
Train with MrSQM
```
clf = MrSQMClassifier()
clf.fit(X_train,y_train)
```

Make predictions
```
predicted = clf.predict(X_test)
```

More examples can be found in the *example* directory. The full UEA and UCR Archive can be downloaded from http://www.timeseriesclassification.com/.


This repository provides supporting code, results and instructions for reproducing the work presented in our publication (under review):

"MrSQM: Fast Feature Selection for Time Series Classification with Symbolic Representations", Thach Le Nguyen and Georgiana Ifrim
