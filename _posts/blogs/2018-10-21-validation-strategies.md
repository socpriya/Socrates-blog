---
layout: post
title:  The three important Cross-Validation techniques
category: blog
keywords: cross validation, Hold-out, hold out, K-fold, K fold, Leave-one-out, Leave one out, cv, LOO, LOOCV
---
Cross-Validation (CV) is a model evaluation technique to compute the performance of a Machine Learning (ML) model. After building a model, validating it on trained data fetches the residual errors, and one should never use the same data to measure the quality of a model. It is required to validate it against the unseen data to arrive at the actual performance. Following are the three important CV techniques that are widely used in the industry to measure the performance:
{: .text-justify}

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**1. Hold-out**<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**2. K-Fold**<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**3. Leave-One-Out (LOO)**

Let us take a look at each one of them in detail.

**1. Hold-out:**
In this technique, the given dataset is split into Train and Test datasets in random. Usually, the split ratio varies from 70:30 to 90:10. The model is trained on the train set and validated on the test set. The performance of the model is computed using _predicted outcome_ and _actual value_ of the test dataset.
{: .text-justify}

![hold-out]({{site.baseurl}}/assets/img/hold-out.jpg)
{: .text-center}
<br>
<script src="https://gist.github.com/socratesk/b9f6124276bca737b0069fc69b26c5ce.js"></script>

Hold-out CV is a widely used technique when the dataset is large. The drawback with this technique is the randomness of the data that may lead to overfitting. Think of a scenario where the dataset is small, and after splitting the train set contains people from a particular state/gender, and the test set has different state/gender.
{: .text-justify}

**2. K-Fold:**
In this technique, the given dataset is split into an equal number (K) of folds. The split may either be _Random_ or be _Stratified_. The model is iteratively trained on _**K-1**_ folds and tested on the fold that is not included for training. Though there is no formula, the number of folds (K fold) varies from 5 to 10 depending on the size of the dataset.
{: .text-justify}

![k-fold]({{site.baseurl}}/assets/img/k-fold.jpg)
{: .text-center}

In the above picture, the given dataset is split into 5 folds equally. In the first iteration, folds 1, 2, 3, and 4 are used for training a model (Model 1) and fold 5 is used for prediction. In the second iteration, folds 1, 2, 3, and 5 are used for training (Model 2) and fold 4 is used for prediction. This process is carried out iteratively for all the 5 folds. Based on the _predicted values_ and _actual targets_ of each fold, the accuracy of each model (fold) is computed and averaged for _mean accuracy_.
{: .text-justify}

<script src="https://gist.github.com/socratesk/dffa1ff9d1b7bdb48bb68649104c3614.js"></script>

> In a _Random split_, as the name implies, the dataset is split in random. The drawback with this approach is, there may be an imbalance in _target_ feature in each fold. In other words, one or more of the folds may have very less or only one _target_ feature than the other folds. Unlike random split, the _Stratified split_ ensures that there is the same amount of distribution of _target_ features in each fold.
{: .text-justify}

The advantage with this technique is that each data point is tested as unseen data and is participated _**K-1**_ times in the training process. This technique eliminates the _randomness_ bias stated in the Hold-out method. This method best works for small and medium size datasets.
{: .text-justify}

The main drawback with this approach is that the time taken to train and test the model increases by _**K-1**_ times when compared to _Hold-out_ technique. For instance, in 5-fold CV the time taken is at least 4 times higher than the hold-out approach.
{: .text-justify}

**3. Leave-One-Out (LOO):**
Leave-One-Out is a special case of K-Fold technique in which the K becomes N. The dataset is split into N folds where N is the total number of data points in the dataset. The models are trained N separate times using N-1 data points, and the prediction is made on the left-out data point. This method best works for small size datasets.
{: .text-justify}

The code for K-Fold can be used for LOO as well with below updates:
{: .text-justify}

<script src="https://gist.github.com/socratesk/aa186220853be6154ec4810fa46d064e.js"></script>

<br>
**Conclusion:** To increase the accuracy of a model using any of the above CV techniques, [fine-tune the hyper-parameters](https://en.wikipedia.org/wiki/Hyperparameter_optimization){:target="_blank"} of the model using the [grid search](https://scikit-learn.org/stable/modules/grid_search.html){:target="_blank"}. Refer to my article on [Hyper-parameter Tuning of Machine Learning Models](https://blog.socratesk.com/blog/2018/07/09/hyperparameter-tuning-XGBoost){:target="_blank"} to know more about it. After arriving at optimal parameters, use them to build a final model using the entire dataset as CV is a technique for _Model Checking_ only and not for _Model Building_.
{: .text-justify}
---