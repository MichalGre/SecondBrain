# Simple linear regression


$$ x = b + aX $$

### Example in Python
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

dataset=pd.read_csv('data.csv')
X = dataset.iloc[:,:-1].values
y = dataset.iloc[:,-1].values

from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train,y_train)

y_pred = regressor.predict(X_test)

```