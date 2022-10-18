# Overview 
**House Pricing Prediction starts with Linear Regression way to the Regularized linear model to get the probable price of any house based on its features**.


- Used any relevant functions/ visualization techniques that can help understand the data.
- Loaded the data and performed all necessary data cleaning, scaling, and preprocessing it.
- Explored the selection of various feature variables for **regression** to estimate the `Sale Price`
- Performed various regression analyses using various methods 
	-   Linear regression 
	-   Lasso regression 
	-   Ridge regression 
	-   Polynomial regression
	
- Provided suitable quantitative metrics for assessing the performance of each model based on the required application.

## Code and Resources Used 

**Python Version:** 3.7  
**Packages:** pandas, NumPy, sklearn, matplotlib, seaborn, statsmodels  

**Motivation:** ITI Assignment `Given by eng.Amira Mamdouh`

## `01` EDA
### **My Observations :**
Data suffer from  : 
 1. Nulls
 2. Duplicate values
 3. Highly Correlated Features
 4. Skewness
 5. Outliers 


## `02` Data Preprocessing
I made the following changes and created the following variables:

- **Nulls handling** (because the model needs numerical inputs)

- **Outliers handling** (because the outliers will affect the fitted model):

- **Clamping outliers** because then the model will be fitting the
very large values that cause high loss and the rest of the points will be
under-fitted

- **Skewness handling** (because the skewness makes it more probable to ruin the
assumption of homoskedasticity of residuals)

- **Handling highly correlated features**
(Because highly correlated features are redundant, they don’t add any value to
the model, and cause multi-collinearity which makes the p-values (significance)
of each feature in the regression analysis not reliable)

- **Handling features that have the same values** all the time (they don’t add any
value to the model, you are adding a dimension that is the same as most of the
time…. Useless)

- **Feature scaling**

 1-  **For numerical features:**
 
 (If you did not scale the features, the model will work well and produce
 the same results; however, the coefficients will not be interpretable
 because the units of all variables are not the same)
 
     - If we know that the distribution of the variable is normal,
     standardize the feature, otherwise, the min-max scale
 
 2- **For categorical features:**
 
     -  One-hot-encode the nominal features
     -  Label-encode the ordinal features    

- **Subset selection** (select the significant features only). we need to make sure that the p-value in the significance test of each feature is reliable, and as we mentioned before, the p-values are not reliable if multi-collinearity exists. That’s why we remove the multi-collinearity completely using the `Variance Inflation Factor (VIF)`

-  **Remove the multi-collinearity** we can make backward stepwise subset selection by relying on the p-values (significance test) of each feature.<br> 
`Backward-stepwise subset selection` removes the insignificant features successively; one feature at a time, and that’s why we made a sequential for loop to remove the insignificant features.

## `03` Model Building 

I split the data into train and test sets with a test size of 20%.   

I focused on the tree-based model because it can capture nonlinear relationships without requiring any transformation before and data is already small.  


*	**Linear Regression** – Baseline for the model
*	**Linear Regression** – with subset selection 

          The previous method (subset selection) is very discrete and very aggressive;
          because we either choose the feature to be with us in the model or we
          completely exclude it from the model … so why don’t we try other methods that
          is less aggressive and just reduces the weight of insignificant features? 
          That’s why we will try the shrinkage methods:

*	**Ridge regression**
*	**Lasso regression**
*	**Elastic-Net regression**
 
 
         Tried the previous shrinkage methods with all the possible values of
         Lambda (the regularization parameter), and decide the best lambda for each
         model to get
         
         All the previous models assume that there is a linear relationship between the
         features and the response variable, and we tried to do our best to tune the
         previous models and get the best results out of them, but what if there are no
         linear relationship between the features and the response variable??? Then the
         model assumptions will be ruined.

Therefore, in this step, we need to `check the model assumptions
- Homoskedasticity of residuals
- Normality of residuals and zero-mean of the residuals

      If any of them is ruined, then maybe the relationship between the features and       
      the response variable is nonlinear, and we need to `perform basis expansion` of        
      the features.

- **Perform basis expansion** on the features (start with polynomial degree 2) and
repeat all the previous steps using the new polynomial features

## `04` Model performance

### To sum all the results up, here are the R_squared for all of the models :
<center>


|       Models          | R2 in Train  |R2 in Test  | alpha     | Dergee |
|-------------------    |-------        |-------  |-------    |-------    
| linear Regression Before subset selection    | 0.85701   |  0.827026           |   -       | -|
| linear Regression After subset selection         | 0.82387   |  0.765111   | - |     -|                  
| Ridge Regression      	| 0.857063   |  0.824699	| 0.1   	|   -   |
| Lasso Regression      	| 0.857147   |  0.826586  	|   0   	|   -   |
| Polynomail Regression      	| 1.0   |  0.509571 	|   -   	|   2   |
# ____________________________________________________________________



</center>
