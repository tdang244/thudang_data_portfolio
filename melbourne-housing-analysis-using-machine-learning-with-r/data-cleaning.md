# Data Cleaning

The original dataset: 13580 observations&#x20;

There are three main steps to clean the data:&#x20;

* Step 1: Removing NAs → 6196 observations remain&#x20;
* Step 2: Remove house prices that are out of range (as in Plot 1), which is above 6M AUD → 5 outliers are removed. 6191 observations remain&#x20;
* Step 3: Remove the year built outlier (as in Plot 2), which is under 1800, since most houses are built later than 1800. 6190 observations remain In total, we have removed 7390 rows of data with outliers or with no information.&#x20;

This is justified as we need high-quality data to create good models, and 6190 is a good amount of data to work with.

**Plot Appendix**

![](<../.gitbook/assets/Screen Shot 2021-12-25 at 9.04.48 PM.png>)

![](<../.gitbook/assets/Screen Shot 2021-12-25 at 9.06.51 PM.png>)
