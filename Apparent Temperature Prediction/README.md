
# Overview 
**Predicting the `Apparent temperature` using different regression models**.

- Loaded the data and performed all necessary data cleaning and scaling.  
- Used any relevant functions/ visualization techniques that can help understand the data.
- Explored the selection of various feature variables for **Regression** to estimate the `Apparent temperature
- Performed various classification analysis using various methods 
	-   Linear Regression
	-   SVR Classifier with (Linear kernel) 
	-   Polynomial Regression
- Provided suitable quantitative metrics for assessing the performance of each model based on the required application.


## Code and Resources Used 

**Python Version:** 3.8
**Packages:**  
  > -  pandas
  > - numpy
  > - scipy
  > -  matplotlib
  > -  seaborn 
  > - sklearn
    
 **Dataset:** https://github.com/martandsingh/datasets/blob/master/weatherHistory.csv
 
**Motivation:** ITI Assignment `Given by eng.Amira Mamdouh`

## EDA 
Checked the distributions and have a general look at the data and understand the features.


## Preprocessing 
- Handled highly correlated features by removing the most correlated features (corr > 0.7) and if we have 2 highly correlated features, we drop one of them (the variable which is less correlated to the response variable).
- Clamped outliers for the whole data using their quartiles.	
- Skewness handling using `log transformation`.
- Checked Normality using `Shapiro-Wilk Test` and scale Features using.
  - **Standard scaler** for normally distributed features.
  - **Min Max scaler** for the other features.



## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and test sets with a test size of 20%.   
I tried these models to compare the SVM kernels' behavior VS Linear regression :
*	**Linear regression** 
*	**SVM Regressor with (Linear kernel)** 
*	**Polynomial Regression** 

I used the following to track the model behavior: 
- Mean Absolute Error
- Mean Squared Error 
- R_Squared 
- Adjusted R_Squared).


