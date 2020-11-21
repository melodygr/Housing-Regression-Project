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
Following the OSEMN (Obtain, Scrub, Explore, Model, Interpret) data science framework, we began with an understanding of our business problem and the acquisition of data.  We then followed the iterative process outlined below:  
* Import and Examine Data
* Investigate distribution of variables
* Subset data for business case and recheck distributions
* Check for multicollinearity
* Prepare data for modeling (OHE)
* Remove Data Outliers
* Run baseline model on training set
* Check modeling assumptions
* Eliminate variables not significant to model or multicollinear
* Run second model
* Eliminate variables not significant to model or multicollinear
* Run third model
* Check assumptions and reconfigure variables
* Run fourth model
* Check results against test data for overfitting of the model
* Log transform and scale certain variables
* Run fifth model
* Log transform sales price
* Run sixth model
* Examine polynomial features an/or variable interactions
* Use Recursive Feature Selection (RFE) to determine significant interactions
* Run seventh model
* Revert to previous model and reeximine interactions
* Run eigth model
* Choose best model to fit all assumptions
* Run cross-validation of final model
* Interpret results


<!---![alt text](https://github.com/melodygr/microsoft_movie_analysis/blob/main/images/popularity.png "Genre Popularity Graph")--->

### Conclusions  
* Significant features in  luxury homes include number of bathrooms, waterfront property, location (zip codes, lat and long), public grade and whether the house has been renovated or not
* Having a bigger house in terms of floors or bedrooms does not necessarily imply higher sale price
* Square footage, while important, is not as significant as other factors in terms of pricing (such as location)

### Next Steps / Future Work  
1. Refine dataset (expand and cut certain zip codes)
1. Subset model for different price ranges
1. Apply log and scaling transformations to certain features to account for normality and differing magnitudes
1. Investigate polynomial relationships and interactions between variables in greater detail

