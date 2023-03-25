# Description

A Python Jupyter notebook containing the ML model for binary classification (i.e. death or no death) of data point based on numerous features from a Titanic dataset.

# Pipeline

1. **Read data**
2. **Clean data**
3. **Preprocess data**: one-hot encoding of categorical data, binning, feature selection, normalization
4. **Classic 60-20-20% train-validation-test split**
5. **Train different algorithms** on the train set, check accuracy on validation set, select the algorithms that performs the best on validation set
6. **Finetuning hyperparameters** of the selected algorithm on train+validation set using GridSearchCV
7. **Test set**

# Dependencies

Python version 3.10.6 was used. 

The required Python libraries can be found in `requirements.txt`. The file was generated using the following command in the Bash terminal:
```bash
pip freeze | grep -iE "numpy|pandas|matplotlib|seaborn|scikit-learn" > requirements.txt
```
