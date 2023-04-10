# Milestone-2

Satring the project for milestone-2, i decided to do in collab because my docker wouldnt work on my end, so collab was my next bet.
We used the shap library for this. First I imported all the important libraries such as pandas, xgboost,  and matplotlib.
Then i added the train.csv file and dropped the ID tag because it wasnt necessary in predicting the sale price.
I used the data.fillna and filled it with the mean value of the dataset. Because the dataset had num int values and characters with no value, it was better to drop the columns that didnt have either a int or float value.
Created my X and y, the X was the entire train dataset without the SalePrice, while my y was the SalePrice itself. I used xgboost.XGBRegressor().fit(X,y) to train my mmodel.
Finally used an explainer for the model to produce shap values of X.

The waterfall graph show the shap vlauesand their effects on the final price of the individual house prediction. In my case, I was looking at the first house which had a sale price of $208500, to which my prediction was $208287.109 which is on par wit the actual sales price of the house. By changing the the value within the bracket of the shap_value, it would show a waterfall plot of a different house. 

shap.plots.waterfall(shap_values[0])

Afterwards, I created anotner xgboost model to train another set of X and y for the shap interaction values. 
In this model, I set the learning rate to 0.01, and decided to look at LotArea. The higher it is onm the grap the more it effects the final outcome of the value. 
