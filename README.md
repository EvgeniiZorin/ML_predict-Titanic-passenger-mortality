# Description

A Python Jupyter notebook containing the ML model for binary classification (i.e. death or no death) of data points based on numerous features from a Titanic dataset.

# Background

Sinking of the Titanic was a great tragedy that still resonates with the world. From that horrible event, we have available a dataset for people who were on board of the Titanic, with information available for the seating class, fare paid for the ticket, etc., along with the data on survival. Naturally, this dataset was used by the ML community to see underlying patterns in the data, to be able to predict the survivability of a person based on his attributes from the dataset.

# ML model

The ML model `ML_model_Titanic.sav` accepts the following features in the following order: 

```py
[
	'Pclass', 'SibSp', 'Parch', 'Fare', 
	'Sex_female', 'Sex_male', 
	'Embarked_C', 'Embarked_Q', 'Embarked_S', 'Embarked_U', 
	'Categorized_age_(0, 10]', 'Categorized_age_(10, 20]', 'Categorized_age_(20, 30]', 'Categorized_age_(30, 40]', 'Categorized_age_(40, 50]', 'Categorized_age_(50, 60]', 'Categorized_age_(60, 70]', 'Categorized_age_(70, 80]'
]
```

For this model, I used the following features:
- Pclass
- SibSp
- Parch
- Fare: log normalised
- Sex: one-hot encoded into 2 binary columns
- Embarked: one-hot encoded into 4 binary columns
- Age: binned into 8 columns

Label to be predicted is "Survived" - a binary categorical variable with only two unique values - 0 and 1.  

Accuracy of final model on the test set = 0.827


# Pipeline

1. **Read data**
2. **Data Cleaning**: N/A handling, drop feature "Cabin" with too many missing values
3. **Data Preprocessing**: one-hot encoding of categorical data, binning, feature selection, normalization
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
