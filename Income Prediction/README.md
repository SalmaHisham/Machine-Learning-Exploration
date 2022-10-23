
# Overview 
**Classify the income of the user whether it is above or below 50K `Using Tree-based algorithms and KNN`**.

- Loaded the data and performed all necessary data cleaning and scaling.  
- Used any relevant functions/ visualization techniques that can help understand the data.
- Explored the selection of various feature variables for **classification** to estimate the `Income whether it is above or below 50K`
- Performed various classification analysis using various methods 
	-   KNN 
	-   Decision Tree
	-   Random Forest Tree
- Provided suitable quantitative metrics for assessing the performance of each model based on the required application.


## Code and Resources Used 

**Python Version:** 3.8
**Packages:**  
  > -  pandas
   >  - numpy
   >  - scipy
   > -  matplotlib
   >-  seaborn 
   >- sklearn
    
 **Dataset:** https://www.kaggle.com/code/rohitamalnerkar/adult-dataset-income-prediction/data

**Motivation:** ITI Assignment `Given by eng.Amira Mamdouh`

## EDA 
Checked the distributions and have a general look at the data and understand the features.


## Preprocessing 
- Handled Null values 
- Clamped outliers for the whole data using their quartiles.	
- Dropped duplicates.
- Checked Normality using `Shapiro-Wilk Test` and scale Features using.
  - **Standard scaler** for normally distributed features.
  - **Min Max scaler** for the other features.
 - Encode categorical data 
 - Using `Under-Sampling` to handle imbalanced data.


## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and test sets with a test size of 20%.   
I tuned the model parameters using `Grid Search` to get the best performance for each of the following models:
*	**KNN** 
*	**Decision Tree** 
*	**Random Forest Tree** 

I used the following for evaluation : 
- `classification_report` from sklearn 
-  `Decision tree plot` 



