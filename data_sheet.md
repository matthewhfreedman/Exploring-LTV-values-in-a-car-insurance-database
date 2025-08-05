# Datasheet – Exploring factors affecting lifetime values in a Car Insurance customer dataset

## Motivation

I wanted to choose a regression or classification problem that was relevant to my job as a digital marketer. Working out the lifetime value of customers based on the original data recorded from either the lead or the first transaction is important to businesses. Some companies feed the lifetime value back into the Ads platforms tracking system to allow them to optimise towards potentially higher LTV customers.

According to many accounts on Kaggle the data I used was hosted on the IBM site to showcase their analysis tool called IBM Watson. Originally the dataset was on this URL:

https://www.ibm.com/communities/analytics/watson-analytics-blog/marketing-customer-value-analysis/

But this link has now disappeared along with the original explanation about the data. The link above is now a redirect to IBM’s general marketing blog. Therefore I haven’t got much more to say about this dataset other than a number of people have created data science projects using it and uploaded it to Kaggle as part of learning about the field. For example:

https://www.kaggle.com/datasets/pankajjsh06/ibm-watson-marketing-customer-value-data/data 

The uploaded project on Kaggle above was where I got the data. It was uploaded 6 years ago which means that the data is at least 6 years old.

So in short we don’t know the source of the data, other than it represents car insurance premiums and LTV and was at one stage hosted on the IBM site. This doesn’t rule out the data being “dummy data” created with the intent to test on the IBM’s analysis tools.
 
## Composition

The data is car insurance tabular data with each row representing a customer. It contains typical columns you’d expect from a car insurance customer database including the types of cars insured, the type of insurance they have, the number of policies they have, their location, their income and employment status. In all there are 23 columns. 8 are numeric and 16 are categories. There were no NAs. The number of rows are 9134. Based on the fact that the column “states” includes US states I believe this data is from the United Statess. Monetary figures would be in dollars.

The data was uploaded with customer reference numbers, but without knowing whether the data is real, or from what insurance provider it came from I don’t believe it has traversed any data protection law in any domain. We’d hope that because the data was hosted on the IBM site originally that a large corporate like that would be more compliant with data protection laws, however they would be in line with the data protection laws around 2018-2019 when the dataset became available on Kaggle.

## Collection process

I’m unsure about how this data was acquired. Due to this I won’t use it for anything else other than a learning exercise. I don’t believe you could extrapolate that the features in this dataset that predict LTV could apply to other car insurance datasets.

## Preprocessing/cleaning/labelling

The data seems to have had some preprocessing as there are no NAs in the data. The data however doesn’t apply to the whole USA as the only US states in the State column are Washington, Arizona, Nevada, California, and Oregon. The labels of the columns are clear and easy to understand.

## Uses

The data could be used to practice predicting claims costs per customer as well, as this data was included. The data includes a gender column which could be used to say that one gender was more likely to cost the company in terms of claims compared to the other. In the UK FCA regulations says that you can’t discriminate on the grounds of gender. If gender did have a large impact on LTV, and that was fed back to the Ads platforms then Google would bid different depending on the gender. As it happens correlation between LTV and gender is very low. Marital status is also a column in the data and this could become a proxy for people with a disability or people with the same-sex attraction who are less likely to get married given gay-marriage isn’t legal yet in the US. Again the correlation between LTV and marriage status is fairly low in the dataset. We could remove them however they are barely being used in the models I have created.

## Distribution

The dataset was simply uploaded to Kaggle and left there from it’s original place on the IBM site. There appears to be no copyright or IP and the original place IBM uploaded it to on their site has been removed.  

## Maintenance

The data is not maintained.


