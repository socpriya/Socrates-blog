---
layout: post
title: Prudential Life Insurance - Classification of Risk
category: kaggle
---

This 'Featured' [Kaggle competition](https://www.kaggle.com/c/prudential-life-insurance-assessment) was from [Prudential Life Insurance](http://lifeinsurance.prudential.com/) to assess and identify risk classification of customers based on their extensive personal and medical information. This will help Prudential to shorten their current 30-day turnaround to be fast enough to produce the quote and send it out to customers. The competition ran from 23-Nov-2015 to 15-Feb-2016 and there were 2619 teams who participated across the globe.
{: .text-justify}

In this Supervised Learning, customers' personal and medical information, life insurance product chosen, and actual risk were provided in [Train Data set](https://www.kaggle.com/c/prudential-life-insurance-assessment/data). The _quadratic weighted kappa_, which measures the agreement between two ratings, was used to evaluate and score the Risk prediction. [Refer here](https://github.com/benhamner/ASAP-AES/tree/master/Evaluation_Metrics/R) to understand more about how to evaluate it on predicted value.
{: .text-justify}

To predict the risk classification, I first tried with [Recursive-Partition (rpart) Classification Tree Model](https://github.com/socratesk/kaggle/blob/master/Prudential/1-Classification.R) to understand the performance of this basic model. It scored 0.60115 in Public Leaderboard. After that I built the following set of models:
{: .text-justify}

 * [Random Forest Model](https://github.com/socratesk/kaggle/blob/master/Prudential/2-RandomForest.R) from  ```caret``` library
{: .text-justify}
 
 * [Machine Learning in R Model](https://github.com/socratesk/kaggle/blob/master/Prudential/3%20-%20Machine%20Learning%20in%20R%20(MLR).R) from ```MLR``` library. Used both ```count:poisson``` and ```reg:linear``` objectives with multiple rounds
{: .text-justify}
 
After preparing multiple predictions with various rounds, objectives, and algorithms, I did a _mode_ of all the outputs and arrived at my final submission. Finally, at the end of the competition, I could get into [top <19% (485 out of 2619)](https://www.kaggle.com/c/prudential-life-insurance-assessment/leaderboard/private) in the Private Leaderboard.
{: .text-justify}

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)