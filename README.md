# Optimizing Customer Acquisition and Retention with CLTV Prediction

- The main goal of this project is to forecast the <u> Customer Lifetime Value </u> (CLTV) using user and policy data.

- CLTV: a metric that indicates how much revenue a company can anticipate from a customer over their entire relationship.
    - It aids businesses in understanding the long-term worth of their customers and guides decisions regarding customer acquisition and retention investments.
    - Essentially, CLTV assists businesses in determining the value of each customer over time.

## Dataset Overview

1. **Description, Features, and Attributes:**
    - This dataset contains information on customers and policies, such as the customers' highest qualification, annual income, employment status, chosen policy, policy type, and the target variable indicating the total CLTV.
    - Some key features include:
        - id: Unique customer identifier
        - gender: Customer's gender
        - area: Customer's location
        - qualification: Customer's highest qualification
        - claim_amount: Total amount claimed by the customer (in rupees)
        - vintage: Number of years since the first policy date
        - num_policies: Total number of policies issued to the customer

## Code Related

- Utilized a conda environment with Python version 3.9 (GPU and CUDA enabled).

1. For local setup:
    - Clone the repository: `<repo_name>`
    - Activate the environment: `conda activate venv`

2. "Might require re-installation" Libraries:
    - tensorflow
    - tensorflow-diretml-plugin (GPU-based)
    - fast_ml

## Project Flow

1. **Data Analysis, Preprocessing, and Engineering:**
    - Handled duplicates, missing values, null values, etc., to ensure minimal impact on business analysis.
    - Conducted thorough analysis, including exploring gender ratios to diversify product offerings, investigating factors contributing to higher average claims in urban areas, etc.
    - Utilized statistical tests (1-way ANOVA test) to compare mean CLTV across different categorical variables and understand CLTV variation.
    - Implemented logical data cleaning and transformation techniques.

2. **Models Employed for Prediction:**
    - Linear Regression (complemented with Elastic Net with equal regularization ratio)
    - Random Forest Regressor (complemented with LightGBM)
        - vanilla
        - hyperparameter tuned
    - Deep Neural Network
        - vanilla
        - hyperparameter tuned

## Observations

1. None of the models exhibited exceptional performance, with the Random Forest Regressor slightly outperforming the others.
2. R2 and Adjusted-R2 scores were prioritized to gauge the metrics' influence on the business module.

## Results

- Through EDA and model development, it is apparent that "PLATINUM" policy is favored by a majority of the population regardless of the area, be it rural or urban. So, major focus can be given there for retention.

- Despite the poor performance of the vanilla Random Forest Regressor, the tuned model exhibited significant improvement compared to its predecessor.

- The likely cause for the low metrics could be attributed to the "quality" of the data (DATA QUALITY). Even with thorough preprocessing and engineering, if the data quality is poor, it is expected to yield unfavorable results.

    - Upon deeper investigation into the data source, it was discovered that all attempts at modeling this dataset resulted in similar metrics, underscoring the data's quality issues.
