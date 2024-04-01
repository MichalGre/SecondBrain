## Machine learining - data preprocessing

### Feature scaling techniques

* normalization
$$  X'= \frac{X - Xmin}{Xmax - Xmin} $$

Recommended when we have normal distribution among features

* standarization

$$ X' = \frac{X-\mu}{\sigma} $$
where $\mu$ is a mean and $\sigma$ is standard deviation

Can be used allways :) 

Why use in ML? Because we don't want one feature to dominate on another. In other words it is a method of putting features on the same scale.

```
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
X_train[:,1-4] = sc.fit_transform(X_train[:,1-4:])
X_test[:,1-4] = sc.transform(X_test[:,1-4])
```

### Encoding categories

* Use OneHotEncoder

>One hot encoding is a technique that we use to represent categorical variables as numerical values in a machine learning model.



```
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder

ct = ColumnTransformer(transformers=[('encoder',OneHotEncoder(),[0])],remainder='passthrough')
X = np.array(ct.fit_transform(X))
```
```
[[a a 123]
 [b s 34]
 [c c 321]
 [b z 443]]
```
to
```
[[1.0 0.0 0.0 a 123]
 [0.0 0.0 1.0 s 34]
 [0.0 1.0 0.0 c 321]
 [0.0 0.0 1.0 z 443]]
```