# Project Summary - P6 Final - Regression Analysis
**Author:** Karli Dean

## Dataset Overview
This dataset covers medical costs to insurance policyholders. In this set, we are led to assume this is 1 insurance company only (think of like Blue Cross Blue Shield, etc). This set details each record as the policyholder or main beneficiary and what theri rate is. We have been provided many factors to consider like age, sex, BMI, number of children, if they smoke, and where they're from. I targeted *charges*, which is the continuous value in the dataset.\
\
This dataset has no missing values, so my preparations were focused on understanding correlations between the features.

## Data Exploration
I wanted to understand the data relationally, so I turned to visuals.
- Scatterplots were used to understand outliers
- Countplots were used to determine the weight of the categorical features
  - If a category was 99% one field, it would not matter.
  - Lucky for us, this was not the case. All categories mattered.
- After processing, a correlation heat map was created to spot the numerical relationships.

## Data Processing
In this dataset, there is a lot of categorical variables, so I handled those accordingly.
- I turned the smoker and sex features into binary datasets
- I removed the region category, as a region should not matter for a national level insurance group
- I removed any record that had a BMI more than 2 standard deviations away from the average
  - I did not want my data to be skewed in either direction

## Feature Selection
This dataset has a clear target, called *charges*. This is the rate a policyholder would be paying per term for their insurance.\
I had to decide what features would be used to predict this. I landed on the following:
- The age of the policyholder (`age`)
- The BMI of the policyholder (`bmi`)
- Whether the policyholder smokes or not (`smoker_binary`)

## Models and Performance
I completed 3 models regarding this dataset:
1. Baseline Linear Regression
   - Linear R²: 0.797
   - Linear RMSE: 5314.4186811419395
   - Linear MAE: 3960.05
2. Standard Scaler
   - Scaled Linear R²: 0.797
   - Scaled Linear RMSE: 5314.4186811419395
   - Scaled Linear MAE: 3960.05
3. Polynomial Scaler
   - Third Degree Polynomial R²: 0.875
   - Third Degree Polynomial RMSE: 4173.752430728706
   - Third Degree Polynomial MAE: 2698.72

## Insights
- This model tells us that people who smoke are more likely to have higher insurance rates.
- It also tells us that there is light correlation with higher BMI and insurance rates
- This model could be improved if more insights were available, yet that could put the model at risk of overfitting
