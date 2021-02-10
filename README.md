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

- Use `MinMaxScaler` to scale the numerical data.

- Separate the data into training and testing data.

### Tune Model Parameters

- Use [GridSearch](https://scikit-learn.org/stable/modules/grid_search.html) to tune model parameters.

- Tune model

### Compare Models created

- Using model accuracy and resources used for choosing the best model

### Reporting


