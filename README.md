# Description___

A Python Jupyter notebook containing the ML model for binary classification (i.e. death or no death) of data points based on numerous features from a Titanic dataset.

# Background

Sinking of the Titanic was a great tragedy that still resonates with the world. From that horrible event, we have available a dataset for people who were on board of the Titanic, with information available for the seating class, fare paid for the ticket, etc., along with the data on survival. Naturally, this dataset was used by the ML community to see underlying patterns in the data, to be able to predict the survivability of a person based on his attributes from the dataset.

# Data

Dataset `231017_kaggle` is from https://www.kaggle.com/competitions/titanic/data

# ML models and performance

| Model version | Performance | Notes | Notebook |
| - | - | - | - |
| v1 | 

## v1

Data was split 80-20 to train-test. 

The best model in training was SVC, which in 5-fold CV achieved median F1-score = 0.762. Test set of grid search finetuned model (SVC, C=2, kernel=poly), was F1-score = 0.748. 

## v2

Data was split 80-20 to train-test. 

Checked different models. The chosen model was again SVC, but in the end chose a model based on gradient boosting: 

GradientBoostingClassifier(max_depth=5, min_samples_leaf=15, n_estimators=50), Median training F1-score (5-fold CV): 0.763. Test set, F1-score = 0.786.

## v3

Data was NOT split, so train = 100% data.

GradientBoost(learning_rate=0.5, min_samples_leaf=3, n_estimators=50). On train, 5-fold CV, median F1-score = 0.772.

# Dependencies

Python version 3.10.6 was used. 

The required Python libraries can be found in `requirements.txt`. The file was generated using the following command in the Bash terminal:
```bash
pip freeze | grep -iE "numpy|pandas|matplotlib|seaborn|scikit-learn" > requirements.txt
```
