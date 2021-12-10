# Project 2 - Ames Housing Data and Kaggle Challenge

## Problem Statement

Livable, a young home flipping firm, has interest in expanding the business to residences located in Ames. As part of the data science team in the company, I was tasked to predict house sale prices using Linear Regression Models on historical data collected from 2006 to 2010. 

A successful model would help the company in 
1. Accurately predicting sale prices to identify houses that are undervalued and 
2. Identify key features that could direct decisions in renovations and repair works to increase profit

## Summary
The dataset was thoroughly cleaned through (i) the imputation of missing values, (ii) using log transformation on numerical features to fix skew and (iii) fixing of data types.

The greatest challenge in preparing the data was dealing with multicollinearity. As this project intended to create deliverables from the model coefficients, severe multicollinearity could reduce the precision of the estimate coefficients (i.e. how the unit changes of "independent" variables change the sale price). This was addressed through feature engineering, centering under sklearn scalers and also in the regularisation models.

RMSE (/RMSLE due to the log transformation on sale price) and R2 scores (model's ability to explain variability of sale price) were used to determine the best model in predicting prices. The model with the **lowest error** and **highest R2** score was the Elastic Net regression model. Kaggle evaluated the model to have RMSE of 23990.

## Recommendations

Based on the chosen model's coefficients, we could glean findings in 2 aspects.

### Location
🗺️ Neighbourhoods such as Edwards and South & West of Iowa State University decrease sale price by 6.97% and 4.36% (corroborates the EDA on neighbourhood). Hence, when dealing with houses in that neighbourhood, spendings has to be done more prudently.\
🗺️ Houses near parks/greenbelts would result in ~11% increase in sale price.

### Renovation works
🏠 Brick Face exteriors results in a 14.9% increase in sale price\
🏠 Mansard roof styles should be avoided where possible (results in a 9.86% decrease in sale price)\
🏠 Increasing the group living area by building annexes may be risky as even though a 1% increase in living area would result in 0.127% increase in sale price, further cost-benefit analysis is required to determine if there would be profits in doing so.

Currently, the model is useful in picking prime locations or neighbourhoods which require more prudent planning. The next step to build on profits from renovation would require a companion analysis on labour and material costs to predict profitability of the renovations.

**Caveats**
1. This model is based on 2006-2010 data but market trends and residential architecture trends can fluctuate across the years. More data collection would be required to factor in market trends but the team can further build upon the modelling with data from 2011 to now.
2. Further statistical analysis could be conducted to further fix multicollinearity issues and increase precision of coefficients. This would be very important especially when it affects cash flows in the thousands. The model focused on bivariate correlations but can be improved on by analysing the variance inflation factor.

## Data Dictionary

The detailed data dictionary of the data set can be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).
