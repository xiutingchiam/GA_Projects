# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Ames Housing Data and Kaggle Challenge


### Problem Statement

Real estate was once considered a relatively safe harbor, an asset class marked by steady value creation and predictable trends. Those days are over. New technologies and urgent sustainability concerns are now disrupting the industry in ways that raise the stakes for every home buyer and seller.

A realty company that does property sale listings for home sellers, is looking into using Machine Learning to help their clients to predict the sale prices of their homes. With the help of a good prediction model, the company will be able to help clients set a more accurate and realistic price for their home sales. As part of the realty's data science team, we have been tasked with using Machine Learning to build a house sale price prediction model based on the Ames Housing Dataset collected from 2006 to 2010. This dataset contains a total of 2051 rows and 81 columns of data.

---

### Background

Based on a United States Census Bureau report in 2010, Ames, Iowa had a population of approximately 59,000. Also, Ames, Iowa economy and demographics is largely defined by the Iowa State University, a public research university located in the middle of the city. More than 75% of Ames' population is either studying as a student or working as a faculty at Iowa State University, making Ames one large extended campus (more information at this website). Therefore, it isn’t surprising that Ames's largest employer is Iowa State University, which employed approximately 20% of total employment. Hence, just like many college towns, Ames' real estate market is defined by a substantial proportion of rental properties, explaining the housing market's stability in Ames. ([source](https://nycdatascience.com/blog/student-works/predicting-housing-prices-in-ames-iowa-6/))

---

### Datasets

Ames Housing datasets (2006 - 2010) collected from from the Ames, Iowa Assessor’s Office.

* [`train.csv`](../datasets/train.csv): (2016 - 2010) Ames Housing dataset from the database
* [`test.csv`](../datasets/test.csv): (2016 - 2010) Ames Housing dataset from the database, excluding target variable

Data Dictionary of above data sets can be found in this [link](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt))

Dataset with selected features for building the final prediction model.
* [`final_model.csv`](../datasets/final_model.csv)

---

### Data Dictionary for the Final Model Dataset

|Feature|Type|Dataset|Description|
|---|---|---|---|
|saleprice|<i>float</i>|final_model|Sale Price of the House in US$| 
|lot_frontage|<i>float</i>|final_model|Linear street area connected to the house in square feet| 
|lot_shape|<i>int</i>|final_model|Rating of the general shape of the house| 
|overall_qual|<i>int</i>|final_model|Rating of the overall material and finish of the house| 
|year_remod/add|<i>int</i>|final_model|The year which the house was remodeled or have additions added to the house (Year is the same as construction year if no remodeling or additions)| 
|mas_vnr_area|<i>float</i>|final_model|Masonry veneer area in square feet| 
|bsmt_qual|<i>int</i>|final_model|Rating of the basement based on the height of the basement (The greater the height, the higher the rating) Rating of 0 means no basement| 
|electrical|<i>int</i>|final_model|Rating of the electrical system| 
|wood_deck_sf|<i>float</i>|final_model|Wood deck area in square feet| 
|open_porch_sf|<i>float</i>|final_model|Open porch area in square feet| 
|bsmt_exposure|<i>int</i>|final_model|Rating based on the access to walkout or garden level walls, rating of 0 means no basement| 
|bsmtfin_type_1|<i>int</i>|final_model|Rating of basement finished area, rating of 0 means no basement| 
|heating_qc|<i>int</i>|final_model|Rating of heating quality and condition|
|kitchen_qual|<i>int</i>|final_model|Rating of kitchen quality| 
|totrms_abvgrd|<i>int</i>|final_model|Total rooms above grade (does not include bathrooms)| 
|fireplace_qu|<i>int</i>|final_model|Rating of fireplace quality, rating of 0 means no fireplace| 
|garage_yr_blt|<i>int</i>|final_model|Year which garage was built| 
|garage_finish|<i>int</i>|final_model|Rating of the interior finish of the garage, a rating of 0 means no garage| 
|garage_area|<i>float</i>|final_model|Garage area in square feet| 
|garage_qual|<i>int</i>|final_model|Rating of garage quality, rating of 0 means no garage|
|paved_drive|<i>int</i>|final_model|Rating of paved driveway| 
|house_age|<i>int</i>|final_model|Age of the house| 
|house_area|<i>int</i>|final_model|Total area of the house in square feet, including basement| 
|location|<i>int</i>|final_model|Rating of the location of the house|
|total_bath|<i>float</i>|final_model|Total number of bathrooms. Half bath is counted as 0.5 bathroom| 
|ms_subclass_30|<i>int</i>|final_model|House that is under the category of 1-Story, 1945 & older| 
|ms_subclass_60|<i>int</i>|final_model|House that is under the category of 2-Story 1946 & Newer| 
|ms_zoning_RM|<i>int</i>|final_model|Zoning category is Residential Medium Density| under ms zoning|
|mas_vnr_type_None|<i>int</i>|final_model|Indicates that house has no masonry veneer|
|foundation_PConc|<i>int</i>|final_model|Age of the house| 
|foundation_CBlock|<i>int</i>|final_model|House foundation in Poured Contrete category under foundation type| 
|central_air_Y|<i>int</i>|final_model|Indicates if house has central air or not|
|garage_type_Attchd|<i>int</i>|final_model|Garage location is in the attached to the house category under garage type| 
|garage_type_Detchd|<i>int</i>|final_model|Garage location is in the detached from the house category under garage type| 
|sale_type_New|<i>int</i>|final_model|House is in the just constructed and sold category under sale type| 

---

### Executive Summary
01_EDA_and_EDA consists of the first steps in the project workflow which includes data cleaning and EDA. Data cleaning includes understanding each of the individual features, checking for NaN values and imputing them in the best possible manner based on our assumptions. Wrong data types were corrected, incorrect data were replaced, and values in ordinal features were mapped to numerical ratings. Features were grouped into categories, continuous, discrete, ordinal, and categorical data were indentified and EDA was then conducted to explore the relationship between the sale price and each individual feature. Boxplots were plotted to visualize the categorical and discrete features against sale price whenever possible, scatter plots were plotted to visualize continuous features for comparison against sale price and for identifying and removing outliers. Heatmaps were plotted for numeric features to visualize the correlation coefficiency between sale price and these features.

Our next step was 02_Preprocessing_and_Feature_Engineering, where new features were engineered to reduce dimensionality of the data and to account for the patterns and clusters that emerged during EDA. Sale price was logged to make it more normally distributed for modeling. Multicollinearity between indvidual features were identified and removed. Categorical features were dummified for further analysis on their individual correlation coefficiency with saleprice. Different methods of feature selection were used for identifying potential features to be used in the prediction of sale price.   

Our final step was 03_Modeling, where the baseline model was built, along with the linear regression, ridge regression, lasso regression, and elastic net regression. These models were built using different sets of features that were selected in the 02_Preprocessing_and_Feature_Engineering notebook. A score table consisting of each model's RMSE and Cross Validation scores was created for Model Evaluation. Interpretations and recommendations were then made based on the best performing prediction model.

---

### Conclusion 
![Score Table](https://github.com/xiutingchiam/GA_Projects/blob/main/project_2/images/score_table.jpg)
With a RMSE score of 21861.556, the linear regression model using 34 features selected using Pearson Correlation Coeeficient method outperforms the other models. This is a strong improvement over our baseline model's RMSE score of 78,278.841. This model will hence be selected as the final model for our prediction model. (This linear regression model also received a private RMSE score of 22441.732 on Kaggle)

---

### Recommendation
While working on the dataset, the team noticed that the original dataset from Ames, Iowa Assessor’s Office includes data on the condition of sale that provides us with information on whether a sale is a normal sale, an abnormal sale, partial sale where home was not completed when last assessed, sale between family members and etc. This is important because partial sales and sales between family members most likely do not represent actual market values. These kind of observations should be removed from the dataset as this can affect the accuracy of the model. Therefore, it is recommended that we should collect this data and do further analysis on whether it will improve the RMSE score of our model.








