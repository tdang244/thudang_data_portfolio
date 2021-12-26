# Regression - The Process and Results

![Regression Method](<../.gitbook/assets/Screen Shot 2021-12-25 at 9.07.42 PM.png>)

After using the linear model to generate housing price predictions, I plotted the predicted results and the associated residual on a residual plot, which showed non-linear patterns (i.e. the blue line does not match up with the red line)

![Residual plot for values fitted with linear regression](<../.gitbook/assets/Screen Shot 2021-12-25 at 9.10.06 PM.png>)

After that, I decided to use GAM to model the housing price for more accurate predictions. In order to do that effectively, I used LASSO to pick out the top predictors that have the most impact on the housing price.&#x20;

![Picking the most optimal penalty for LASSO](<../.gitbook/assets/Screen Shot 2021-12-25 at 10.01.39 PM.png>)

![Top 6 predictors using LASSO at the most optimal penalty](<../.gitbook/assets/Screen Shot 2021-12-25 at 10.00.48 PM.png>)

Finally, after using GAM, the residual plot is improved significantly since the GAM model captures the non-linearity in using the top 6 variables to predict house prices in Melbourne.&#x20;

![Using GAM to capture the non-linearity in housing price prediction](<../.gitbook/assets/Screen Shot 2021-12-25 at 10.03.32 PM.png>)

![Residual plot for GAM-predicted results](<../.gitbook/assets/Screen Shot 2021-12-25 at 10.04.24 PM.png>)
