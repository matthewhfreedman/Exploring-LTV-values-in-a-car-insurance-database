# Exploring the lifetime value of customers on a car insurance customer database 

As a digital marketer I know that predicting the lifetime value of customers based on the initial purchase data is often worthwhile. Some customers will return their order and get a refund whilst others will become repeat purchasers. This means that some customers are worth spending more on in terms of promotions and adspend per conversion than others. The lifetime value of customers can also be fed back into Google Ads, Microsoft and Meta Ads to improve their algorithmic bidding. In this project I aim to create models to predict lifetime value using data from a car insurance customer database. The lifetime value outputs are for feeding back into the ads platforms as online conversions happen.

## DATA

I found the dataset below which had been posted on Kaggle. It had previous been hosted on the IBM website however it has since been removed. It has lifetime values as one of the columns along with other columns associated with car insurance, e.g. car size, income and policy level. The link to the dataset is here
https://www.kaggle.com/datasets/pankajjsh06/ibm-watson-marketing-customer-value-data/data
Note that I developed the models without looking at how other people had approached the dataset. 

## MODEL 

I tested a huge range of models using the sklearn library including:
- MLP Regressor
- Linear Regression
- Lasso Regression
- Ridge Regression
- Decision Trees
- Ada Boost Regressor
- Random Forest Regressor
- Support Vector Regressor
- Gradient Boosting Regressor

Random Forest Regressor was chosen as the optimal model when using default parameters. I chose it because the lifetime values it predicted were closest to the actual LTV values that I was trying to predict.

## HYPERPARAMETER OPTIMSATION

I carried out hyperparameter tuning on 

- Random Forest Regressor
- MLP Regressor
- Gradient Boosting Regressor

I was able to further improve the performance of the model, and the best model was still the random forest regressor.


## RESULTS

After testing different models, and then testing hyperparameters we have achieved a model with a RMSE 3,737 USD when using the kfold method and 2,153 when using a test train split method. RMSE could be seen as the average deviation from the true value. 

If we had simply used the average mean to predict the LTVs we would have a RMSE of 7,051.87. 

This optimal model was a Random Forest Regressor with parameters of max_depth: 15, max_features: None, min_samples_split: 2, n_estimators: 200 and then with all the other default parameters. Creating the model certainly improved the predicted LTV compared to just taking the mean average. 

When I looked at the real LTVs of under 10,000 USD using the train test split method RMSE fell to 1300.83 USD. The predicted LTVs that were most out of kilter were the ones where actual LTVs were already large. I believe if these values were fed into Ads platforms it still would give them the right signals to their algorithms to bid efficiently. 

There are a spate overestimates in the area of 6,000 - 10,000. For those actual LTVs under 6000 USD almost all the differences between the actual figures and the predicted ones were below 500. When put into production it may be worth reducing a predicted LTV of over 30,000 to 30,000 to stop outliers causing the Ads platforms bidding algorithms astray. That said these "black box" algorithms may already have systems to down weight outliers.

## KEY FEATURES

The key features were the monthly premium amount the customers played and the number of policies they had. I did attempt to create a model using only the 5 most important features however I found performance got worse. Including the less important features still had a positive impact on predictive accuracy.


## CONTACT DETAILS

My name is Matthew Freedman and I can be contacted on matthewfreedman@hotmail.co.uk. Please follow me on Linkedin at https://www.linkedin.com/in/matthewppc/


