# House-Prices

# Introduction

The focus in this project is to answer two key questions: 
1.- What are the most important factors that determine a house's price?
2.- Can I predict house values based on these factors?

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

(Image) 

Since I only had one centered normal distribution I apply a natural logarithm to transform the distributions, with that transformations I obtain 7 parameters **(Grade, Sqft lot, Bedrooms, Bathrooms, Sqft living, Sqft above, Sqft backyard)**. 

(Image) 

After, I use a correlation matrix to select the best variables:

(Image) 

Observing the correlation matrix I look for independent variables correlated with price **(r > 0.3)** and I find 5 parameters **(Grade, Bedrooms, Bathrooms, Sqft living, Sqft above)**, then I look for strongly independent variables correlated between each other **(r > 0.7)** and select the one with the highest correlation to the dependent variable. 

At the end I keep only 3 variables: Bedrooms, Bathrooms and Grades. Once I had the most relevant variables I implemente the model. 

# Model Implementation 

I use a Random Forest Regressor with Python default options. With this model I obtain a **MAPE = 13.44%** and an **Accuracy = 86.56%**

(Image) 

# Summary 

I could answer my two key questions 

* What are the most important variables that define a house price?
**I identified the main parameters to predict the house value (grade, bathrooms and bedrooms)**

* Can I predict a house values based on that variables?
**I develop a model capable to predict with 87% precision a house price  with only 3 input parameters**
