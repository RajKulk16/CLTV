# CLTV

- The primary objective of this project is to predict the Customer Lifetime Value (CLTV) based on the user and policy data.

- CLTV : measure that tells businesses how much money they can expect to earn from a customer throughout their entire relationship.
    - It helps companies understand the long-term value of their customers and make decisions about how much to invest in acquiring and retaining them.
    - Essentially, CLTV helps businesses figure out how valuable each customer is over time.

## Dataset Overview

1. **Description, Features and Attributes:**
    - This is a sample dataset of a company holding information of customers and policies such as the highest qualification of the user, total income earned by a customer in a year, employee status, policy opted by the user, type of policy and so on and the target variable indicating the total cltv.
    - Some of the features are as follows - 
        - id-Unique identifier of a customer
        - gender-Gender of the customer
        - area-Area of the customer
        - qualification-Highest Qualification of the customer
        - claim_amount-Total Amount Claimed by the customer (in rupees)
        - vintage-No. of years since the first policy date
        - num_policies-Total no. of policies issued by the customer

## Code Related

- Used conda environment and 3.9 python version (gpu enabled).

1. For running in the local machine - 
    - git clone <repo_name>
    - conda activate venv

2. Libraries (might) have to be installed - 
    - tensorflow
    - tensorflow-diretml-plugin (gpu-based)
    - fast_ml

## Flow of the Project

1. **Data Analysis, Preprocessing, Engineering:**
    - Addressed duplicates, missing values, null values, etc., ensuring its impact on business analysis.
    - Conducted in-depth analysis, including ratio-distribution of gender for diversification of product offerings, potential reasons for higher average claim in the urban areas and many more. 
    - Conducted statistical tests (1-way ANOVA test) to compare the mean CLTV across different categorical variables to observe the degree to which CLTV will vary across these columns. 
    - Performed logical data cleaning and transformation.

2. **Models used for prediction:**
    - Linear Regression (complemented with Elastic Net with equal regularization ratio)
    - Random Forest Regressor (complemented with LightGBM)
        - vanilla
        - hyperparameter tuned
    - Deep Net
        - vanilla
        - hyperparameter tuned

## Observations

1. None of the models performed very well, with Random Forest Regressor slightly performing better than others. 
2. Emphasis was placed on R2 and Adjusted R2 score for clarity on metrics' impact on the business module. 

## Result

- Based on EDA and model development, it is evident that most of the population choose "PLATINUM" policy irrespective of the area - rural, urban.

- Despite the extremely poor performance of vanilla Random Forest Regressor, the tuned model performed much better when compared to its predecessor.