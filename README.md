# Machine Learning - Exoplanet Exploration

[Background](#Background) | [Data Source](#DataSource) | [Model Creation](#MachineLearningModelCreation) | [Reporting](#Reporting)

## Background

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. To help process this data, machine learning models will be created in order to capable of classifying candidate exoplanets from the raw dataset.

## Data Source

[Kepler Exoplanet Search Results](https://www.kaggle.com/nasa/kepler-exoplanet-search-results): This dataset is a cumulative record of all observed Kepler "objects of interest" — basically, all of the approximately 10,000 exoplanet candidates Kepler has taken observations on.

## Machine Learning Model Creation

View Script -> [Logistic Regression](exoplanet_exploration/Testing/logistic_regression.ipynb) | [Support Vector Classification](exoplanet_exploration/Testing/svc.ipynb) | [Random Forest](exoplanet_exploration/Testing/random_forest.ipynb) | [Deep Learning](exoplanet_exploration/Testing/deep_learning.ipynb)

### Preprocess the raw data

- Preprocess the dataset prior to fitting the model.

- Perform feature selection and remove unnecessary features.

    * Apply `RFE` method to identify the importance of ecah feature.
    
    * Select only the features that support the outcome. 

- Use `MinMaxScaler` to scale the numerical data.

- Separate the data into training and testing data.

### Tune Model Parameters

- Use [GridSearch](https://scikit-learn.org/stable/modules/grid_search.html) to tune model parameters.

- Tune model

### Compare Models created

- Using model accuracy and resources used for choosing the best model

## Model Selection Report

<a align="center" href="https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html" target="_blank"><img alt="Estimator Flowchart" src="Images/ml_map.png" /></a>

As the flowchart presented above, the model that would be the best estimator for prediction of candidate exoplanets is **Linear SVC (Support Vector Classification)** as the following assumptions.

- The model will predict catagorial output (y).

- y is a labeled data.

- There are less than 100K samples in the dataset.

After training and fitting model with selective features, applying GridSearchCV to tune the best model with different parameters. The result show that the best parameter is **'C': 1000, 'gamma': 1, 'kernel': 'linear'** with **88.23%** accuracy.

```javascript
# Defining parameter range 
param_grid = {'C': [0.1, 1, 10, 100, 1000],  
            'gamma': [1, 0.1, 0.01, 0.001, 0.0001], 
            'kernel': ['linear']}  

grid = GridSearchCV(model, param_grid, refit = True, verbose = 3)

>> Output
>> Best Parameter: {'C': 1000, 'gamma': 1, 'kernel': 'linear'}
>> Best Model Score: 0.8832746927280798
```

**Model Summary**

<p align="center">
  <img src="Images/svc_summary.png">
</p>