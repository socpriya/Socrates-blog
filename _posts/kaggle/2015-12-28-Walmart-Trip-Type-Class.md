---
layout: post
title: Walmart Recruiting - Trip Type Classification
category: kaggle
---

This recruitment competition was with Walmart through [Kaggle](https://www.kaggle.com/c/walmart-recruiting-trip-type-classification) to categorize and classify customers' trips to their stores - whether it was a daily dinner trip, weekly grocery trip, special holiday gift trip, or for seasonal clothing purchase. In fact, this was a **Multi-class Classification Probabilities** competition in which the probability of each classification has to be predicted for each trip by a customer and recorded in Test Dataset, after learning from the Train Dataset. 
{: .text-justify}

The competition ran from 26-Oct-2015 to 27-Dec-2015 and 1047 members participated in total. Being recruitment competition, forming of teams was not allowed and the number of participants were lower than other 'featured' competitions. 
{: .text-justify}

Personally, I like recruitment competitions because no code sharing is allowed in the competition's public forum. That encourages participants to come-up with their own logic and algorithm selection.
{: .text-justify}
 
In this competition, **Multi-class logarithmic loss** was used to evaluate the performance of predicted probabilities. 
{: .text-justify}

![screenshot]({{ site.baseurl }}/assets/img/MCLL.png)

To predict the probabilities, I used Random Forest with 4-fold repeated cross-validation. It is important to set ```classProbs=true``` in ```trainControl``` object before passing it into RF model for multi-class probabilities.
{: .text-justify}

```trcontrol <- trainControl(method = "repeatedcv", number = 4, repeats = 2, verboseIter = FALSE, returnResamp = "all", classProbs = TRUE)```

The complete code for Random Forest model can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Walmart-1/2-RandomForest-FeatureEngg.R).

<center>- - - - -</center>

A good thing with XGBoost algorithm is that it has a built-in **mlogloss** evaluation metric type that can be passed as a parameter while training the data. 
{: .text-justify}

```xgbcv <- xgb.cv(param = list('objective' = 'multi:softprob', 'eval_metric' = 'mlogloss', 'num_class' = noOfClasses), data = trainMatrix, label = Target, nrounds = cv.round, nfold = cv.nfold)```

The complete code for my XGBoost model can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Walmart-1/1-XGBoost-FeatureEngg.R).
<br>

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)