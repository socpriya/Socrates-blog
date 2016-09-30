---
layout: post
title: Rossmann Store - Sales Forecasting
category: kaggle
---

This was my first-ever [Kaggle competition](https://www.kaggle.com/c/rossmann-store-sales) in which the daily sale of 1,115 Stores located across Germany has to be forecasted for next 6 weeks using promotions, school and state holidays, seasonality, locality of store, and competitor data. The competition was running from 30-Sep-2015 to 14-Dec-2015 and 3303 teams were participated. In this Supervised Learning, the sale of previous 2 years 6 months data were given as [Train Data](https://www.kaggle.com/c/rossmann-store-sales/data) set, and Root Mean Square Percentage Error (RMSPE) metrics was used to evaluate and score the prediction.

![screenshot]({{ site.baseurl }}/assets/img/RMSE-RMPSE.png)

Being first competition, it was challenging to understand the competition ecosystem and dynamics. I became a forum-dweller for couple of weeks reading all the posts and replies, and then created my first model in R using basic Linear Model algorithm. This scored 0.61328 in Private leaderboard and here is the [Code](https://github.com/socratesk/kaggle/blob/master/Rossmann/1-LinearModel.R) in Github.

A good thing about reading Forum posts is, you will get to know plenty of other algorithms that are not taught in regular courses. One such algorithms is XGBoost (Extreme Gradient Boosting). As someone stated in the [Forum](https://www.kaggle.com/c/rossmann-store-sales/forums), it is the algorithm that gives out Gold even when you pass garbage as Input. Tried using ```XGBoost``` with minimal feature engineering on this data set.

```
# Extract Day, Month, and Year from Date object and then remove Data object
merged_train$Day   <- day(merged_train$Date)
merged_train$Month <- month(merged_train$Date)
merged_train$Year  <- year(merged_train$Date)
merged_train$Date  <- NULL

# Separate Sales figure from merge data and convert it to log scale to bring down its dimensionality.
merged_train$Sales <- log1p(merged_train$Sales)
```

The complete code with Feature Engineering can be found in Github [here](https://github.com/socratesk/kaggle/blob/master/Rossmann/2-XGBoost-FeatureEngg.R).

This Github [link](https://github.com/socratesk/kaggle/blob/master/Rossmann/2-XGBoost-FeatureEngg.R) contains another flavor of XGBoost with Feature Engineering and Parameter Tuning.

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)