# House-Prices

# Introduction

The focus in this project is to answer two key questions: 
* What are the most important factors that determine a house's price?
*  Can I predict house values based on these factors?

To address these questions, I did this plan of action:
* Monitor house prices and their characteristics.
* Download a comprehensive database containing this information.
* Utilize market research and statistical techniques to identify the most relevant variables (Methodology).
* I will apply a machine learning model to predict house prices using only the identified relevant variables (Results).

# Metodology 

## Market Research 

From Market Research I realize what people look the most in a house is: 
* Good location
* Security
* Space
* Distribution
* Facade
* Illumination

I associate this parameters with my dataset variables and obtain:
* Good location: Coordinates (latitude ,longitude)
* Security: Condition, Grade
* Space: Sqft lot
* Distribution: Bedrooms, Bathrooms, Sqft living, Floors, Sqft above, Sqft basement, Sqft backyard
* Facade: Year built
* Illumination: View

After I identify these variables I start with the statistical techniques to obtain the most relevant parameters related to the house price.

## Statistical Techniques 

First, I examine the distribution of the variables to ensure that maintains a centered normal distribution (like grade) 

![First_Paramaters_Distributions](https://github.com/user-attachments/assets/91788435-a55c-4d21-bf8b-414e26fe4392) 

Since I only had one centered normal distribution I apply a natural logarithm to transform the distributions, with that transformations I obtain 7 parameters **(Grade, Sqft lot, Bedrooms, Bathrooms, Sqft living, Sqft above, Sqft backyard)**. 

![Transformed_Parameters_Distributions](https://github.com/user-attachments/assets/d1dfd938-d32c-445a-9092-34982cf9f758)

After that, I use a correlation matrix to select the best variables:

![Correlation_Matrix](https://github.com/user-attachments/assets/9c343c96-fee8-45aa-a23c-04ee26346142)

Observing the correlation matrix I look for independent variables correlated with price **(r > 0.3)** and I find 5 parameters **(Grade, Bedrooms, Bathrooms, Sqft living, Sqft above)**, then I look for strongly independent variables correlated between each other **(r > 0.7)** and select the one with the highest correlation to the dependent variable. 

At the end **I kept with only 3 variables: Bedrooms, Bathrooms and Grades**. Once I had the most relevant variables I implement the model. 

# Model Implementation 

I use a Random Forest Regressor with Python sklearn default options. In the next image I show my model residuals.

![Model_Residuals](https://github.com/user-attachments/assets/2840eef6-8bf3-4057-b020-2b5c53ce1cd4)

 With this model I obtain a **MAPE = 13.44%** and an **Accuracy = 86.56%**

# Summary 

I could answer my two key questions 

* What are the most important variables that define a house price?
**I identified the main parameters to predict the house value (grade, bathrooms and bedrooms)**

* Can I predict a house values based on that variables?
**I develop a model capable to predict with 87% precision a house price  with only 3 input parameters**
