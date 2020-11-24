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


![Data Heatmap](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/heatmap.png "Heat Map")

![Pair Plot](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/multicolinear_pairplot.png "Pair Plot")

![QQ Plot](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/baselineQQplot.png "QQ Plot")

![Logged_Histograms](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/logged_histograms.png "Logged Histograms")

![Transformed](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/transformed.png "Transformed")

![Predictions](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/predictions.png "Predictions")

![Predictions_Test](https://github.com/swzoeller/Housing-Regression-Project/blob/main/images/predictions_test.png "Predictions Test")

### Conclusions  
* Significant features in  luxury homes include waterfront property, location (zip codes, longitude), and square foot above ground
* Having more floors or bedrooms does not necessarily imply higher sale price
* Bottom Line: location and square footage are the most important features in determining sale price

### Next Steps / Future Work  
1. Refine dataset (expand and cut certain zip codes)
1. Subset model for different price ranges
1. Investigate polynomial relationships and interactions between variables in greater detail

