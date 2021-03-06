---
description: Customer Segmentation with K-Means Clustering
---

# Getting acquainted with the Data

### Data Source

The data that I'll be using is a popular public dataset on Kaggle called 'Mall Customer Segmentation Data', which can be found at this link

{% embed url="https://www.kaggle.com/vjchoudhary7/customer-segmentation-tutorial-in-python" %}

### A look at the data

The dataset has 5 columns x 200 rows

![Source: Kaggle](../.gitbook/assets/screen-shot-2021-06-27-at-12.17.23-pm.png)

* Customer ID: Unique ID assigned to the customer
* Gender: Gender of the customer
* Age: Age of the customer
* Annual Income \(k$\): Annual Income of the customer
* Spending Score \(1-100\): Score assigned by the mall based on customer behavior and spending nature. The higher the score is, the more the customers spend. 

I will start by performing K-Means Clustering on 2 variables, and then increase the number of variables gradually.

