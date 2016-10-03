---
layout: post
title: Walmart Recruiting - Trip Type Classification
category: kaggle
---

This recruitment competition was from Walmart through [Kaggle](https://www.kaggle.com/c/walmart-recruiting-trip-type-classification) to Categorize and Classify customers trip to their stores - whether it is a daily Dinner trip, weekly Grocery trip, special Holidy Gift trip, or for seasonal Clothing purchase. In fact this was a **Multi-class Classification Probabilities** competition in which the probaility of each classification has to be predicted for each trip by a customer and recorded in Test Data, after learning from Train Data. The competition was running from 26-Oct-2015 to 27-Dec-2015 and 1047 members were participated in total. Being recruitment competition, forming of teams was not allowed and the no of participants were lower than other 'Featured' competitions. 

Personally I like recruitment competitions because no code sharing is allowed in competition's public forum that helps participants to come-up with their own logic and algorithm selection.
 
In this competition, **Multi-class logarithmic loss** was used to evaluate the performance of predicted probailities. 

![screenshot]({{ site.baseurl }}/assets/img/MCLL.png)

To predict the probabilities, I used Random Forest with 4 fold repeated cross-validation. It is important to set ```classProbs=true``` in traincontrol object before passing it into RF model for multi-class probabilities.

```trcontrol <- trainControl(method = "repeatedcv", number = 4, repeats = 2, verboseIter = FALSE, returnResamp = "all", classProbs = TRUE)```

The complete code for Random Forest model can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Walmart-1/2-RandomForest-FeatureEngg.R).

<center>- - - - -</center>

A good thing with XGBoost algorithm is, it has a built-in **mlogloss** evaluation metric type that can be passed as a parameter while training the data. 

```xgbcv <- xgb.cv(param = list('objective' = 'multi:softprob', 'eval_metric' = 'mlogloss', 'num_class' = noOfClasses), data = trainMatrix, label = Target, nrounds = cv.round, nfold = cv.nfold)```

The complete code for XGBoost model can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Walmart-1/1-XGBoost-FeatureEngg.R).
<br>

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)