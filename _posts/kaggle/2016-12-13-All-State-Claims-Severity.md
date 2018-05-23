---
layout: post
title: Allstate Insurance Company - Prediction of Severity of Insurance Claims
category: kaggle
---

This time [Allstate Insurance Company](https://www.allstate.com/) sponsored a "recruitment" competition in [Kaggle](https://www.kaggle.com/c/allstate-claims-severity) to predict cost of insurance Claims so that the severity of a Claim can be determined in an automated way. The determination of Claims severity will improve _Claim Service_ that Allstate provides to its customers, which in turn will improve the Customer Experience for the 16 million households it protects today.
{: .text-justify}

The competition ran from 10-Oct-2016 to 12-Dec-2016 and there were 3055 individuals who participated across the globe.
{: .text-justify}

The [dataset]( https://www.kaggle.com/c/allstate-claims-severity/data) comprised of 116 categorical and 14 continuous features. The “loss” feature given in the train dataset is the one that had to be predicted from test dataset. **Mean Absolute Error (MAE)** -  measure of how close the predicted values are to the eventual outcomes or actuals, was used to evaluate and score the loss prediction. Refer to any of my code files in [Github - Allstate folder](https://github.com/socratesk/kaggle/tree/master/Allstate) for its implementation.
{: .text-justify}

![screenshot]({{ site.baseurl }}/assets/img/MAE.png)

To test my submission file and to know where I stand in Public Leaderboard, I prepared a quick and dirty [XGBoost Model](https://github.com/socratesk/kaggle/blob/master/Allstate/1-Basic-XGBoost.R) with basic and default parameters. After that I built the following set of models to ensemble:
{: .text-justify}

 * [Generalized Boosted Regression Model (GBM)](https://github.com/socratesk/kaggle/blob/master/Allstate/2-GBM.R) with Out-of-Bag (OOB) estimator, _Gaussian_ distribution, and 5-fold cross-validation
{: .text-justify}
 
 * [5 H2O Deep Learning Models](https://github.com/socratesk/kaggle/blob/master/Allstate/3-H2O%20Deep%20Learning.R) each with 2 levels of hidden layers, 20 epochs, _Huber_ distribution, and _Rectifier_ activation
{: .text-justify}
 
 * 10 folds of [MXNet](http://mxnet.io/) [Deep Learning Models](https://github.com/socratesk/kaggle/blob/master/Allstate/4-MXNet.R) each with 2 levels of hidden layers and _one-hot encoding_
{: .text-justify}
 
 * [ExtraTrees Model](https://github.com/socratesk/kaggle/blob/master/Allstate/5-ExtraTrees.R) with _one-hot encoding_ and 3 random cuts for each feature
{: .text-justify}

 * [XGBoost Model](https://github.com/socratesk/kaggle/blob/master/Allstate/6-XGBoost-FeatureEngg.R) with parameter tuning and feature engineering
{: .text-justify}

After creating the above models, I took a simple average of all the predictions. Then I ensembled by applying different weightage to each model's predictions, cross-validated, and then submitted. Finally, at the end of the competition, I could get into [top 20% (604 out of 3055)](https://www.kaggle.com/c/allstate-claims-severity/leaderboard/private) in Private Leaderboard. 
{: .text-justify}

Refer below for first few rows of submission file:

| id | loss     |
|----|----------|
| 4  | 1626.451 |
| 6  | 2034.433 |
| 9  | 10186.82 |
| 12 | 6364.859 |
| 15 | 838.1675 |
| 17 | 2330.886 |
| 21 | 2103.839 |
| 28 | 902.1843 |
| 32 | 2544.185 |
| 43 | 3245.454 |

One of the key challenges with this competition was the size of the data, after _feature engineering_ and _one-hot encoding_. In order to process the data and generate the models, I used the [Domino Data Lab's](http://dominodatalab.com/) computing platform. For most of the above models, I chose **Medium Hardware Tier** (4 core. 16GB RAM) costing around $40.
{: .text-justify}
![screenshot]({{ site.baseurl }}/assets/img/underscore.png)