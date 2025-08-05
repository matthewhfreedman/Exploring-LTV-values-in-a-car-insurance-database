# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:**

State (US State)
Response
Coverage (Cover Level)
Education (Level)
Effective To Date
EmploymentStatus
Gender
Income
Location Code
Marital Status
Monthly Premium Auto
Months Since Policy Inception
Number of Open Complaints
Number of Policies
Policy Type
Policy
Renew Offer Type
Sales Channel
Vehicle Class
Vehicle Size

**Output:**

Customer Lifetime Value

**Model Architecture:**

Random Forest Regressor using Sklearn
Optimal parameters were

max_depth': 15
max_features: None
min_samples_split: 2 (default)
n_estimators': 200

All the other paramters were default ones

## Performance

Performance metrics can change everytime you run it.

In my last run I got these results

RMSE (K-Fold) - 3730.23
All below usign train test split method
RMSE - 2145.70
R2 - 0.90
MAPE - 0.065
MAE - 923.89
Spearman Rank - 0.979

This compares to the mean predictor RMSE of 6918.45 and a mean predictor MAPE of 0.74

Predicted lifetime values were on average larger when the real lifetime value was also larger.

## Limitations

Can only work if the columns required for the model are available. A single missing column isn't an issue can be filled in using an algorithm unless it is Number of Policies and Monthly Premium Auto which are the most important columns.

## Trade-offs

The residuals of the real LTVs vs the predicted ones are higher for larger real LTVs. Due to this I believe that if put into production any prediction of over 30,000 should be flattened to 30,000 before upload to Ads Platforms.
