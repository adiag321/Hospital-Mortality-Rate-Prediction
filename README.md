# <p align = 'center'>Hospital-Mortality Rate Prediction</p>

Hospital Mortality is a serious topic which is a life and death event thus in this project I am studying the hospital data and patient information to predict hospital mortality. The dataset is highly imbalanced with the target class distribution shown below:

![classImb](https://user-images.githubusercontent.com/51110015/113250728-0c57ee80-928f-11eb-980b-9997c5f64be3.PNG)

I have perform the initial steps of Data Cleaning, feature engineering, removed anomalies from the data and then performed modeling. I am using two standard baseline models to observe the model performance with the unbalanced dataset which we observed in the previous plot. The aim is the predict whether patient dies or survives in the hospital from the models:

- Logistic Regression
- Random Forest

![LR](https://user-images.githubusercontent.com/51110015/113250881-550fa780-928f-11eb-9346-bbbe7e592902.PNG)

![RF](https://user-images.githubusercontent.com/51110015/113250884-550fa780-928f-11eb-8128-82c0839d2302.PNG)

Observations From the model's results we can make following observations:

Logistic Regression: From the confusion matrix of logistic regression, we can say that we are getting a very good prediction for the negative class which is survivor class (99 % recall) but our model is also not able to predict the true positive i.e. died In-hospital class (12 %). we also have a high false negative (88 %) which is bad for our us. Our aim should be to increase True positives prediction and decrease false negatives. We can say our model is predicting the died-in-hospital as survived due to the data imbalance.

Random Forest: Our random forest model is also giving similar results, with only 28% True positives and 95% true negatives with very high false negative which should be less.

Over Sampling

I further tried oversampling technique to handle the data imbalance. I am using SMOTE for oversampling. SMOTE(Synthetic Minority Oversampling Technique) is the most widely used approach to synthesizing new examples. SMOTE works by selecting examples that are close in the feature space, drawing a line between the examples in the feature space and drawing a new sample at a point along that line. Synthetic over-sampling works to cause the classifier to build larger decision regions that contain nearby minority class points.

I got the following results:

![LR_smote](https://user-images.githubusercontent.com/51110015/113252059-50e48980-9291-11eb-826d-c7490ee4e238.PNG)

![RF_Smote](https://user-images.githubusercontent.com/51110015/113252060-50e48980-9291-11eb-8cbb-735b7ca2a262.PNG)

Observation: I made the following observations for both the models:

Logistic regression: From the confustion matrix of logistic regression, we can say even though our true negative decreased to 76% but our true positive which is the more important class have increased to a very high value (72%) which is a very good number that our logistive regression model is giving after over sampling. We can further perform feature engineering and use advance models to increase this accuracy further.

Random Forest: Even though logistic regression performed well with oversampling Random forest couldn't perform very well in this case giving the true positives around 46% only.

We can choose logistic regresion as the final model in this case.
