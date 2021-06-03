# Class 13 Reading NOtes

## How to Run Linear Regression in PY

- **scikit-learn** is a powerful python modules for machine learning

- contains regression, classification, clustering, model selection, and dimensionality reduction

### Exploring Boston Housing Data set

- requiured imports 
  - numpy
  - pandas
  - scipy.stats
  - matplotlib.pyplot
  - sklearn

```py
from sklearn.datasets import load_boston
boston = load_boston
```

- boston is a dictionary

- explore keys of dictionary with boston.keys

### Scikit Learn

- fit a linear regression model and predict the boston housing prices

- first, import linear regresion from sci-kit learn module

```py
from sklearn.linear_model import LinearRegression
```

- LinearRegression and the <tab> key wil give a list of functions available

- **important functions**
  - lm.fit() - fits a linear model
  - lm.predict() - predict y using linear model
  - lm.score() - returns coefficient

### Training and Validation data sets

- How to do train-test split

- function called
  - train_test_split

