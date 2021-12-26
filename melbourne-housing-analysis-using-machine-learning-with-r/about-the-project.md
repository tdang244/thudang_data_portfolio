# About the Project

The R code and code appendix for this project can be found [here](https://github.com/tdang244/Melbourne-Housing-Analysis) on my GitHub.&#x20;

### Context

As a final deliverable for my Statistical Machine Learning course, I performed two analyses on [the Melbourne housing dataset on Kaggle](https://www.kaggle.com/anthonypino/melbourne-housing-market) using Machine Learning techniques with R.

My motivation to analyze a housing dataset is Simpson's Paradox. I remembered seeing for the first time a Simpson’s paradox related to a housing dataset in my first Statistical Modeling class. It was pretty eye-opening to get very counter-intuitive results, and later discover the lurking variables that cause the controversy. I have learned to be much more critical in statistical modeling and machine learning due to those occurrences, and I hope to stumble upon some in this dataset.

![](https://lh3.googleusercontent.com/Wim9MXzudLgImHrzbq20-g\_VB1KNCJgOWbTRla8-EUbYszR-gWzFacNPcIvA5giN2dn07AlLVtUw3m6h0BlndzR0yqRqGuEzmuI3GZYjl2vmoTTW\_EFlszq--Sv3HAb2XaDbmZAkIM7s)

I conducted two types of analyses with three different research questions:

* Regression: _How can we predict the price of Melbourne houses?_
  * I first fit an ordinary least square (OLS) model with a linearity assumption to predict the house price. I then plotted the residuals of the predictions against the real values to see if there are any patterns of non-linearity. Next, I used LASSO to select the top 5 variables that matter in price prediction and fit the _Generalized Additive Model_ (GAM), which is a non-linear model, to better capture the non-linearity pattern in the data for more accurate prediction. &#x20;
* Clustering: _How many different groups of houses are there in Melbourne?_
  * I first identified the optimal number of clusters using the Elbow Method, then fit the data with the K-means algorithm to identify the count and the characteristics of separate clusters.&#x20;

### Result

* Regression&#x20;
  * Housing prices cannot be modeled with pure linear regression as there are non-linearity patterns in the data. Therefore, non-linear models like GAM should be used to better capture the non-linear patterns for more accurate predictions.&#x20;
  * In the Melbourne housing data that I used, the number of rooms, building area, house type, the number of bathrooms, year built, and distance from the Sydney Central Business District are the top predictors to model housing prices for Melbourne houses.&#x20;
* Clustering
  * I identified and characterized three distinct clusters of houses in the dataset.&#x20;
