---
layout: post
title: The Winton Stock Market Challenge - Predicting Future (Stock Returns)
category: kaggle
---

Another recruitment competition [hosted by Kaggle](https://www.kaggle.com/c/the-winton-stock-market-challenge) for a British Investment Management Firm **[Winton](https://www.wintoncapital.com/en/home)**, to predict the _intra_ and _end of day_ returns of the stocks based on historical stock performance and masked features. The competition was running from 27-Oct-2015 to 26-Jan-2016 and 832 members were participated in total. Like any other recruitment competitions, forming of teams was not allowed in this too. 

In this competition, **Weighted Mean Absolute Error** was used to evaluate the performance of predicted Stock Returns. The R code for this evaluation metrics can be found [here](https://www.kaggle.com/wiki/Code)

![screenshot]({{ site.baseurl }}/assets/img/WMAE.png)

Working with this competition was bit more challenging since there were 211 features and the _Train data set_ was ~173 MB. 

Since the preparation of output file was taking hours together to process I had to work with R code to the *load* data and *calculate* results, and Java code to *format* and *prepare* final submission file.

- Median Replacement - [R Code](https://github.com/socratesk/kaggle/blob/master/Winton/1-MedianRepl.R); [Java Code](https://github.com/socratesk/kaggle/blob/master/Winton/1_Output.java)
- Median Replacement - 3% Adjusted - [R Code](https://github.com/socratesk/kaggle/blob/master/Winton/2-Adjusted_3perc_MedianRepl.R)
- Moving Average on Test data - [R Code](https://github.com/socratesk/kaggle/blob/master/Winton/3-MovingAverage.R); [Java Code](https://github.com/socratesk/kaggle/blob/master/Winton/3_Csvfile.java)
  
![screenshot]({{ site.baseurl }}/assets/img/underscore.png)