---
layout: post
title: Prudential Life Insurance - Classification of Risk
category: kaggle
---

This 'Featured' [Kaggle competition](https://www.kaggle.com/c/prudential-life-insurance-assessment) was from [Prudential Life Insurance](http://lifeinsurance.prudential.com/) to assess and identify risk classification of customers based on their extensive personal and medical information. This will help Prudential to cut-short the time from 30 days to fast enough to produce the quote and send to customers. The competition was running from 23-Nov-2015 to 15-Feb-2016 and 2619 teams did participate. 

In this Supervised Learning, personal and medical information of customers, life insurance product chosen, and actual risk of them were provided in [Train Data set](https://www.kaggle.com/c/prudential-life-insurance-assessment/data). The _quadratic weighted kappa_, which measures the agreement between two ratings, was used to evaluate and score the Risk prediction. [Refer here](https://github.com/benhamner/ASAP-AES/tree/master/Evaluation_Metrics/R) to know more about how to evaluate it on predicted value.

To predict the risk classification, first tried with Recursive-Partition (rpart) Classification Tree Model to know the performance of this basic model. It scored 0.60115 in private LB. The complete code for ```rpart``` model can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Prudential/1-Classification.R).


I used Random Forest provided by ```caret``` package for Classificaiton. The complete code can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Prudential/2-RandomForest.R).

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)