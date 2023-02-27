# BH-PCMLAI-Module11

This repository contains the practical application assignment for Module 11.
Additional details are provided in this activity's Juniper Notebook.

Notebook link: <LINK URL>


## Methodology

The activity is based from the CRISP-DM framework which follows the following high-level steps:
1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation
6. Deployment
   
<center>
    <img src = images/crisp.png width = 50%/>
</center>


    
### Business Understanding
    
This step will allow us to create a goal based on the current needs of an individual/organization.
The goal for this activity is:

`To determine the best parameters that will be used in creating an optimum model that will predict the appropriate value for used cars`
    
### Data Understanding

This step will allow us to have a general understanding of data by analyzing relationships, identify data quality issues, and create visualizations about the features found in the data set. Based on this activity, we would want to predict the sale price of cars and as such, this is a Regression problem.
    
<center>
    <img src = images/sklearn_algo_cs.png width = 50%/>
</center>	
	

### Data Preparation
    
This step will ensure that the data has been preprocessed and that it has been prepared before performing any modeling activities. For this project, I have used the following preprocessing techniques:
    
1. General data cleaning
    - The overall data set entries are `426880` records
       - There is a feature named `VIN` - where VIN is a unique ID that identifies a vehicle
       - With this, I have removed duplicate VIN records and have been left out with `248099` records
       - The removal of VIN has also allowed further insights that some columns are not relevant with car price
    - Some features that are irrelevant to the car price analysis have been removed accordingly
       - This has been brought by insights during data review, such as that of VIN, features that are not meaningful to
         the analysis, features that have excessive NaN values, and features that have excessive amount of categories
         (i.e., `model` feature with 24k from original 29k after an attempt to clean the data)
       - The data removed was a calculated risk to improve overall performance of the model
           - To give emphasis, removing the model feature represents a significant loss in data. Other than the fact that the number of categories are excessive, there are also mispelled entries which adds up to the complexity of cleaning it. I have attempted to clean this up using `manual checks and SpellCheckers` but to no avail.
    
2. Feature Encoding
    - Most features in this data set are categorical in nature. As such, I have used the `Target encoding` function to ensure that categorical variables are represented as numerical in nature.

3. Logarithmic Transform
    - Most features appears to be skewed and in an attempt to normalize values, I have performed `log` transform to the features

4. Iterative Imputation
    - Many features have values that are NaN. These NaN represents around ~20% (or below) of each feature records in this data set. The use of Iterative Imputation will allow automatically populating of these NaN values to allow a more meaning data analysis.
    
5. Scaling
    - To prepare the data set for modeling, I have performed `scaling` to the data set to improve overall performance and reduce variance to all features (i.e., setting reference to a mean = 0)

### Modeling
    
This step will focus on creating models to predict the car price based on testing data set.
For this activity, I have selected to create two distinct models the follow the following:

Models: 
1. Ridge
2. Lasso

Pipeline Steps: 
1. Polynomial feature expansion
2. Sequential feature selection
3. Model Regression
    
To automate the process, a GridSearchCV object is used to iterate over a predefinied dictionary of parameters to acquire the best model. Based on the GridSearchCV training:
    
 *< Results >
    
### Evaluation
    
- Determine the best validation scheme to score the model
    - HO or KFold (Leave one out is out of the picture as the data set is large)
    - MSE, MAE, and/or RMSE    

### Deployment




#### Findings/Conclusion

<Description of Findings/Conclustion>



#### Recommendation
<Description of Actionable Items>

