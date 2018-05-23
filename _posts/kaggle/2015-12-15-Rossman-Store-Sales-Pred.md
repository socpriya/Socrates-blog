---
layout: post
title: Rossmann Store - Sales Forecasting
category: kaggle
---

This was my first-ever [Kaggle competition](https://www.kaggle.com/c/rossmann-store-sales) in which the daily sale of 1,115 Stores located across Germany had to be forecasted for the next 6 weeks using promotions, school and state holidays, seasonality, locality of store, and competitor data. The competition ran from 30-Sep-2015 to 14-Dec-2015 and 3303 teams  participated. In this Supervised Learning, the sale of previous 2 years 6 months data were given as the [Train Dataset](https://www.kaggle.com/c/rossmann-store-sales/data), and Root Mean Square Percentage Error (RMSPE) metric was used to evaluate and score the prediction.
{: .text-justify}

![screenshot]({{ site.baseurl }}/assets/img/RMSE-RMPSE.png)

Being first competition, it was challenging to understand the competition ecosystem and dynamics. I became a forum-dweller for a couple of weeks reading all the posts and replies, and then I created my first model in R using basic Linear algorithm. This scored 0.61328 in Private leaderboard and here is the [Code](https://github.com/socratesk/kaggle/blob/master/Rossmann/1-LinearModel.R) in Github.
{: .text-justify}

A good thing about reading Forum posts is that you will get to know plenty of other algorithms that are not taught in regular courses. One such algorithm is XGBoost (Extreme Gradient Boosting). As someone stated in the [Forum](https://www.kaggle.com/c/rossmann-store-sales/forums), it is the algorithm that gives out Gold even when you pass garbage as Input. I tried using ```XGBoost``` with minimal feature engineering on this data set.
{: .text-justify}

```
# Extract Day, Month, and Year from Date object and then remove Data object
merged_train$Day   <- day(merged_train$Date)
merged_train$Month <- month(merged_train$Date)
merged_train$Year  <- year(merged_train$Date)
merged_train$Date  <- NULL

# Separate Sales figure from merge data and convert it to log scale to bring down its dimensionality.
merged_train$Sales <- log1p(merged_train$Sales)
```

The complete code with Feature Engineering can be found in my Github [here](https://github.com/socratesk/kaggle/blob/master/Rossmann/2-XGBoost-FeatureEngg.R).
{: .text-justify}

This Github [link](https://github.com/socratesk/kaggle/blob/master/Rossmann/2-XGBoost-FeatureEngg.R) contains another flavor of XGBoost with Feature Engineering and Parameter Tuning.
{: .text-justify}

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)