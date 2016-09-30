---
layout: post
title: Rossmann Store - Sales Forecasting
category: kaggle
---

This was my first-ever [Kaggle competition](https://www.kaggle.com/c/rossmann-store-sales) in which the daily sale of 1,115 Stores located across Germany has to be forecasted for next 6 weeks using promotions, school and state holidays, seasonality, locality of store, and competitor data. The competition was running from 30-Sep-2015 to 14-Dec-2015 and 3303 teams were participated. In this Supervised Learning, the sale of previous 2 years 6 months data were given as [Train Data](https://www.kaggle.com/c/rossmann-store-sales/data) set, and Root Mean Square Percentage Error (RMSPE) metrics was used to evaluate and score the prediction.

![screenshot]({{ site.baseurl }}/assets/img/RMSE-RMPSE.png)

Being first competition, it was challenging to understand the competition ecosystem and dynamics. I became a forum-dweller for couple of weeks reading all the posts and replies, and then created my first model in R using basic Linear Model algorithm. This scored 0.61328 in Private leaderboard and here is the [Code](https://github.com/socratesk/kaggle/blob/master/Rossmann/1-LinearModel.R).

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)