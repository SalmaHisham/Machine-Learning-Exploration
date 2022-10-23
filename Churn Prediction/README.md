
# Overview 
**Binary Classification by SVM and Logistic Regression to get the customers who will probably churn**.

- Loaded the data and performed all necessary data cleaning and scaling.  
- Used any relevant functions/ visualization techniques that can help understand the data.
- Explored the selection of various feature variables for **classification** to estimate the `Churn Chance`
- Performed various classification analysis using various methods 
	-   Logistic Regression
	-   SVM Classifier with (Linear, polynomial, RBF) kernels
- Capture  **(at least 75% of the churners)** to decrease his opportunity loss as much as possible.
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
    
 **Dataset:** Provided in the Repo

**Motivation:** ITI Assignment `Given by eng.Amira Mamdouh`

## EDA 
Checked the distributions and have a general look at the data and understand the features.

## Preprocessing 
- Clamped outliers for the whole data using their quartiles.	
- Skewness handling using `log transformation`.
- Checked Normality using `Shapiro-Wilk Test` and scale Features using .
  - **Standard scaler** for normally distributed features.
  - **Min Max scaler** for the other features.
 - Classify categorical features into (ordinal and nominal) to decide which features will be `Label Encoded` and which features should be `OHE`.
- Encode categorical data  
- Using `Under-Sampling` to handle imbalanced data.


## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and test sets with a test size of 20%.   
I tried these models to compare the SVM kernels' behavior VS Logistic regression :
*	**Logistic regression** 
*	**SVC with (Linear, polynomial, RBF) kernels** 

I used the following for evaluation : 
- `classification_report` from sklearn 
-  `ROC Curve` 
- `Confusion matrix`


