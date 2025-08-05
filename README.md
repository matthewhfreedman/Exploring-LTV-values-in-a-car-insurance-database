# Exploring the lifetime value of customers on a car insurance customer database 

As a digital marketer I know that predicting the lifetime value of customers based on the initial purchase data is often worthwhile. Some customers will return their order and get a refund whilst others will become repeat purchasers. This means that some customers are worth spending more on in terms of promotions and adspend per conversion than others. The lifetime value of customers can also be fed back into Google Ads, Microsoft and Meta Ads to improve their algorithmic bidding. In this project I aim to create models to predict lifetime value using data from a car insurance customer database. The lifetime value outputs are for feeding back into the ads platforms as the conversions happen.

## DATA

I found a dataset which I linked to below which had been posted on Kaggle. It had previous been hosted on the IBM website however it has since beeen removed. It has lifetime values as one of the columns along with other columns associated with car insurance, e.g. car size, income and policy level. The link to the dataset is here
https://www.kaggle.com/datasets/pankajjsh06/ibm-watson-marketing-customer-value-data/data
Note that I developed the models without looking how other people had approached the dataset. I may, once published look at how others approached it.

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

Random Forest Regressor was chosen as the optimal model. I chose it because the lifetime values it predicted were closest to the actual LTV values that it was trying to predict.
To explain Random Forests the model creates a number of decision trees splitting groups of rows in the dataset based on the columns e.g. monthly premium auto, number of policies, car type etc. and then takes the average output. This has been proven to provide great accuracy in predicting values.

## HYPERPARAMETER OPTIMSATION
I carried out hyperparameter optimisation. Whilst we can pick the best model with the default settings, we also have the opportunity to improve the performance of the model by changing a number of the settings within the model. In the industry these are called hyperparameters. I chose the top 3 models to tune. They Random Forest Regressor, Multi-layer Perceptron regressor and Gradient Boosting Regressor.

For the random forest regressor I chose to test n_estimators, which is the number of trees the model makes, of which it will take the average output. I also chose to test max_features which is the maximum features per tree when looking for the best split. max_depth was chosen, which is the maximum depth of each tree allowed. min_samples_split was also a parameter tested for and is the minimum rows left in a node of the tree for it to considered for another split.

For MLP Regressor (multi-layer perceptron regressor) we tuned hyperparameters typical to a neural network. max_iter is number of times during the training of the model that weights are adjusted and the data is passed through the neural network. We also tuned learning_rate_init which tunes how larger change to the model's weights is made in each iteration of the model. A larger learning rate may result it completely missing where the best weights of neural networks are, whilst if it is too small it may take longer to train and it may never converge on the best weight in the neural network.

For the gradient boosting regressor which is also a decision tree based regressor I used n_estimators  max_depth both which were mentioned above and learning rate which in this context is the weighting added to each tree as it builds the model.

## RESULTS

After testing different models, and then testing hyperparameters we have acheived a model with a RMSE 3,737 USD when using the kfold method and 2,153 when using a test train split method. RMSE could be seen as the average deviation from the true value. If we had simply applied the average mean to every LTV value we would have a RMSE of 7,051.87. This optimal model was a Random Forest Regressor with parameters of max_depth: 15, max_features: None, min_samples_split: 2, n_estimators: 200 and then with all the other default paramaters. Creating the model certainly improved the predicted LTV compared to just taking the average. When I looked at the real LTVs of under 10,000 USD  using train test split method RMSE fell to 1300.83. The predicted LTVs that were most out of kilter were the ones where actual LTVs were already large. I believe if these values were fed into Ads platforms it still would give the right signals to their algorithms to bid efficently. The model results in a spate over estimates in the area of 6,000 - 10,000 USD. For those actual LTVs under 6000 USD almost all the differences between the acutal figures and the predicted ones were well below 500. When put into production it may be worth reducing predicted LTVs of over 30,000 to 30,000 to stop outliers leading the Ads platforms bidding algorithms astray. That said these "black box" bidding algorithms may already have systems to down-weight outlier inputs.


## CONTACT DETAILS

My name is Matthew Freedman and I can be contacted on matthewfreedman@hotmail.co.uk. Please follow me on Linkedin at https://www.linkedin.com/in/matthewppc/






