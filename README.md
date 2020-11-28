# King County Real Estate Model

<img src= 
"images/skyline.jpg" 
         alt="Seattle Skyline Image" 
         align="right"
         width="200" height="200"> 

Flatiron Data Science Project - Phase 2  
Prepared and Presented by:  **_Sarah Zoeller_** and **_Melody Peterson_**  
<!---[Presentation PDF](https://github.com/melodygr/microsoft_movie_analysis/blob/main/presentation.pdf "Presentation PDF")  --->

### Business Problem    
King County Real Estate is a luxury real estate company serving sellers and buyers in the high income earning areas of King County, Washington. The company wants to understand which features translate to higher housing prices in these areas, as well as develop a model to predict price based on housing features.

### Data    
This project uses the King County House Sales dataset, which can be found in kc_house_data.csv in the data folder in this repo. The description of the column names can be found in column_names.md in the same folder. In an effort to narrow the scope of the data to suit our business problem, we also obtained census data of individual income tax returns by zip code for the state of Washington.  An editted version of this data can be found in agi_zip_code.xlsx in the data folder in this repo.  The cleaning and selection of relevent data from this dataset can be seen in the [Additional_Data](https://github.com/swzoeller/Housing-Regression-Project/blob/main/Additional_Data.ipynb "Additional Data Notebook") notebook in the repo.

### Modeling Process
Following the OSEMN (Obtain, Scrub, Explore, Model, Interpret) data science framework, we began with an understanding of our business problem and the acquisition of data.  We then followed an iterative process of cleaning and exploring the data, checking for issues with modeling assumptions, creating and testing a model, interpreting the model, and reevaluating the data.

In the initial data exploration, after subsetting the data to the top zipcodes, we checked the distributions of the independent variables for normal distributions.  Although it is not required for the data to be distributed normally, it can result in better models and predictions.

![Subset Distributions](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/subset_distributions.png "Subset Distributions")

Sqft_basement had a place holder value of '?' in 454 entries. Rather than estimating or replacing these values, we are chose to drop these entries. We then cast this column as float instead of object so that we can use the numerical values.

We also checked for multicollinearity among the independent variables and found several variable with high correlations, including: sqft living/sqft above, sqft living/grade, sqft living 15/sqft living, grade/sqft above, bathrooms/sqft living

![Data Heatmap](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/heatmap.png "Heat Map")

"Year renovated" was highly zero-weighted.  We divided this variable into 20 year bins, including a bin for never renovated and a bin for missing values in year renovated.  Date is also stored as a string/object. Since we feel that the date the house was sold may have an impact on the sales price, we are converting it to a datetime object and then converting to an ordinal so we can use it in our model.  Waterfront has a significant number of NaN values. Since we cannot know for certain if the house is on the waterfront, we are casting this variable as a string. It will then have values of '0.0', '1.0', or 'NaN' and we will encode these as categories in our model.  The view variable is described as "Has been viewed". We interpret this to mean that the listing has been viewed in the realtor multiple listing service (MLS) and do not believe that it is relevant to our model.

Once the data had been cleaned we looked at plots of the data to look for linear relationships, normal distributions, and skew caused by outliers.  We can see in these histograms that many of the variables appear to be skewed by abnormally high outliers. Some appear relatively normally distributed. Several are obviously categorical.

Dummy variables that got dropped:

Reno_nan
Waterfront_0.0
Condition_1
Grade_4
Floors_1.0
Bedrooms_1
Zip_98004
Now the results of our model will be changes in price relative to these values.

We will now use IQR to remove price outliers from the dataset before our train test split, and check the new distribution

![Price Distribution](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/outlier_comparison.png "Price Distribution")

Several of the continuous variables were log transformed and scaled to make them more normally distributed and comparable to each other.  

![Logged_Histograms](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/logged_histograms.png "Logged Histograms")

Scaling the variables make them easier to compare to each other as seen in this overlay graph.

![Transformed](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/transformed.png "Transformed")

For our final model, you can see in this graph how our predictions match up with the actual data on which we trained the model as well as on predicting the test data value for Sale Price.

![Predictions](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/predictions.png "Predictions")

![Predictions_Test](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/predictions_test.png "Predictions Test")

By holding all variable except one constant at their mean, we can visualize the relationship between sale price and any given variable as predicted by our model.

![Single Var Plots](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/single_var_plots.png "Single Var Plots")

### Conclusions  
* Significant features in  luxury homes include waterfront property, location (zip codes, longitude), and square foot above ground
* Having more floors or bedrooms does not necessarily imply higher sale price
* Bottom Line: location and square footage are the most important features in determining sale price

### Next Steps / Future Work  
1. Refine dataset (expand and cut certain zip codes)
1. Subset model for different price ranges
1. Investigate polynomial relationships and interactions between variables in greater detail

