---
description: Customer Segmentation with K-Means Clustering
---

# K-Means Clustering with two variables

### Import libraries

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from sklearn.cluster import KMeans
```

### Import dataset

```python
dataset = pd.read_csv('Mall_Customers.csv')
```

![](../.gitbook/assets/screen-shot-2021-06-27-at-12.17.23-pm.png)

### Choose variables to use in K-Means Clustering

As CustomerID is just an arbitrary identifier for customers, it will not help much with identifying the typical characteristics of different customer segments. Therefore, it will be dropped from the dataset. 

In order to grasp the fundamental concepts of K-Means Clustering and see all the relevant steps played out, I will pick out the two variables: _Annual Income \(k$\)_ and _Spending Score \(1-100\)_. These two columns will be stored in the variable X. 

```python
X = dataset.iloc[:, [3,4]].values 
```

### Find the optimal number of clusters using the elbow method

The most 

