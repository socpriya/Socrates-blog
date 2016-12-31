---
layout: post
title: Prudential Life Insurance - Classification of Risk
category: kaggle
---

This 'Featured' [Kaggle competition](https://www.kaggle.com/c/prudential-life-insurance-assessment) was from [Prudential Life Insurance](http://lifeinsurance.prudential.com/) to assess and identify risk classification of customers based on their extensive personal and medical information. This will help Prudential to cut-short the time from 30 days to fast enough to produce the quote and send to customers. The competition was running from 23-Nov-2015 to 15-Feb-2016 and 2619 teams did participate. 

In this Supervised Learning, personal and medical information of customers, life insurance product chosen, and actual risk of them were provided in [Train Data set](https://www.kaggle.com/c/prudential-life-insurance-assessment/data). The _quadratic weighted kappa_, which measures the agreement between two ratings, was used to evaluate and score the Risk prediction. [Refer here](https://github.com/benhamner/ASAP-AES/tree/master/Evaluation_Metrics/R) to know more about how to evaluate it on predicted value.

To predict the risk classification, first tried with [Recursive-Partition (rpart) Classification Tree Model](https://github.com/socratesk/kaggle/blob/master/Prudential/1-Classification.R)  to know the performance of this basic model. It scored 0.60115 in private LB. After that I built the following set of models:

 * [Random Forest Model](https://github.com/socratesk/kaggle/blob/master/Prudential/2-RandomForest.R) from  ```caret``` library
 
 * [Machine Learning in R Model](https://github.com/socratesk/kaggle/blob/master/Prudential/3%20-%20Machine%20Learning%20in%20R%20(MLR).R) from ```MLR``` libray. Used both ```count:poisson``` and ```reg:linear``` objectives with multiple rounds
 
After preparing multiple predictions with various rounds and objectives, and algorithms, I did _mode_ of all the outputs and arrived at final submission. Finally, at the end of the competition, I could get into [top <19% (485 out of 2619)](https://www.kaggle.com/c/prudential-life-insurance-assessment/leaderboard/private) in Private Leaderboard.

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)