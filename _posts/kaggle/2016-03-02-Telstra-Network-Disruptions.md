---
layout: post
title: Telstra - Prediction of Severity of Faults on Telecommunication Network
category: kaggle
---

[Telstra](https://www.telstra.com.au/) is Australia’s largest telecommunications, media, and network technology company, offering a full range of communications services. They conducted their first-ever "recruitment" competition in [Kaggle](https://www.kaggle.com/c/telstra-recruiting-network) to predict the severity of service disruptions on their network - whether it is a momentary glitch or a total interruption of connectivity. The algorithm and model developed for this competition will help Telstra to predict the severity of service disruptions and provide better service to its customers.

The competition ran from 25-Nov-2015 to 29-Feb-2016 and there were 974 individuals participated across the Globe.

The [dataset](https://www.kaggle.com/c/telstra-recruiting-network/data) comprised of multiple files each containing different features extracted from _Log files_, collected from various locations at different time. The target feature, _Fault severity_ with 3 categories _(0: No Fault, 1: Few Faults, and 2: Many Faults)_ is the one that has to be predicted from given datasets. Again, the prediction should be the probability of each severity type _(multi-class)_ for the given test dataset.

In this competition, **Multi-class logarithmic loss** was used to evaluate the performance of predicted multi-class probabilities. 

![screenshot]({{ site.baseurl }}/assets/img/MCLL-Telstra.png)

I generate the following set of models to submit them individually and then to ensemble:

 * [5 Fold cross-validation XG Boost Model](https://github.com/socratesk/kaggle/blob/master/Telstra/1-XGBoost.R)

 * [Generalized Boosted Regression Model (GBM)](https://github.com/socratesk/kaggle/blob/master/Telstra/2-GBM.R) with Out-of-Bag (OOB) estimator, ```repeatedcv```, and 5 separate 10-fold cross-validations
 
 * [Random Forest Model](https://github.com/socratesk/kaggle/blob/master/Telstra/3-RandomForest.R) with Out-of-Bag (OOB) estimator, ```repeatedcv```, and 8 separate 10-fold cross-validations
 
 
Refer below for first few rows of submission file:

| id | predict_0   | predict_1   | predict_2   |
|----|-------------|-------------|-------------|
| 2  | 0.991082892 | 0.007185119 | 0.001731983 |
| 3  | 0.276082613 | 0.609547675 | 0.114369705 |
| 4  | 0.951721534 | 0.044502856 | 0.003775634 |
| 7  | 0.235435281 | 0.231292959 | 0.533271745 |
| 9  | 0.071940752 | 0.187302526 | 0.74075672  |
| 10 | 0.839680135 | 0.126305137 | 0.034014717 |
| 11 | 0.564171374 | 0.428022489 | 0.007806152 |
| 12 | 0.882261053 | 0.110307094 | 0.007431867 |
| 14 | 0.457473055 | 0.532052293 | 0.010474668 |
| 15 | 0.78682138  | 0.207976922 | 0.005201698 |

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)