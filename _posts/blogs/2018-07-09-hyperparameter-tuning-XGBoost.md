---
layout: post
title:  Hyper-parameter Tuning of Machine Learning Models
category: blog
keywords: parameter tuning, tuning, hyperparameter tuning 
---

To improve the performance of a machine learning model, one of the aspects that Data Scientists focus on is, tuning and fine-tuning hyper-parameters of Machine Learning (ML) models, besides working on [*Feature Handling*](http://blog.socratesk.com/blog/2018/06/17/featuren-engineering-and-extraction){:target="_blank"} and *Model Ensemble*. Parameter tuning plays a vital role in achieving higher accuracy of an ML model.  
{: .text-justify}

In this post, we will apply [XGBoost](https://xgboost.readthedocs.io/en/latest/python/python_intro.html){:target="_blank"} algorithm on [Breast Cancer Dataset](http://tunedit.org/repo/UCI/breast-cancer.arff){:target="_blank"} published at [UCI Machine Learning Repository](http://mlr.cs.umass.edu/ml/datasets/Breast+Cancer){:target="_blank"}, tune various parameters, and see how it improves the performance of an ML model.
{: .text-justify}

<object data="{{ site.baseurl }}/assets/pdf/Parameter_Tuning_XGBoost.pdf" type="application/pdf" width="725px" height="600px">
    <embed src="{{ site.baseurl }}/assets/pdf/Parameter_Tuning_XGBoost.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="{{ site.baseurl }}/assets/pdf/Parameter_Tuning_XGBoost.pdf">Download PDF</a>.</p>
    </embed>
</object>

<br>
The initial accuracy of XGBoost model, from the above PDF document, is 73.26% with random parameters. After tuning 6 different parameters, the accuracy increased by 1.16% to 74.42%. Though the increase in accuracy is marginal due to the very small dataset, this document explains how one can tune hyper-parameters using [*GridSearchCV*](http://scikit-learn.org/0.16/modules/generated/sklearn.grid_search.GridSearchCV.html) and improve the performance.
{: .text-justify}

---