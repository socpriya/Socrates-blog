---
layout: post
title:  How to determine the important features using Permutation Importance?
category: blog
keywords: MDA, permutation, permutation importance, PIMP, permutation engineering, Mean Decrease Accuracy
---
One of the widely used techniques to identify all the important features from a given dataset is _Backward Elimination_, which is discussed in the post [How to identify the features that are important for a Machine Learning model?](http://blog.socratesk.com/blog/2018/02/24/feature_importance_and_identification){:target="_blank"}. With this technique, a model has  to be developed each time to determine the importance of all the features and eliminate the least important one. As only one feature gets eliminated during each iteration, the model has to be re-trained every time a feature gets eliminated, till all the insignificant features are removed. This technique is, certainly, a computationally intensive and time-consuming. Think of a situation where there are 100s of features and 10s of 1000s of observations in a dataset, and we want to identify the important features.
{: .text-justify}

**Permutation Importance or Mean Decrease Accuracy (MDA):**

In this technique, a model is generated only once to compute the importance of all the features. Due to this, the Permutation Importance algorithm is much faster than the other techniques and is more reliable.
{: .text-justify}

The following steps are involved, behind the scene:
{: .text-justify}
1. A model is created with all the features in a dataset (This is the only model created)
2. The values in a single feature are randomly shuffled, and predictions are made using the resulting dataset
3. The predicted values are compared with the actual values to compute the performance degradation due to the shuffling (The feature is “important” if shuffling decreases the performance because the model relied on that feature for the prediction)
4. The feature's value is unshuffled to bring it to the original state
5. The steps 2 to 4 are carried out with the next feature in the dataset until the importance of all the features are computed
{: .text-justify}

![RandomShuffle]({{ site.baseurl }}/assets/img/rand_shuffle.png){:height="352px" width="728px"}
{: .text-center}
<center><span style="font-size: 18px;">Random Shuffle of the first feature</span></center>
{: .text-center}
<br>
Let us take a sample dataset [50-Startups.csv](https://github.com/socratesk/data/){:target="_blank"}, run a simple _Random Forest Regressor model_, and compute Permutation Importance.
{: .text-justify}

<script src="https://gist.github.com/socratesk/485e267b875b885024211b158301de99.js"></script>

The above code prints a table with the list of features and weights in descending order, as shown below. The number before the ± denotes how much the model performance decreased with a random shuffling of that particular feature alone. The number after the ± denotes how the performance varied from one reshuffling to the next.
{: .text-justify}

![PermImp]({{ site.baseurl }}/assets/img/perm_imp_weight.png){:height="144px" width="275px"}

**Conclusion:**

Based on the above table, the performance of the model got significantly degraded when `RDSpend` was shuffled, making it the most important one. When the `MarketingSpend` was shuffled, the  performance was degraded to some extent making it the second important one. It is evident that `RDSpend` and `MarketingSpend` are the ones that have more influence in determining the _Profit_ of a startup company. Shuffling of the other features have very less impact on performance, and hence they can be eliminated.
{: .text-justify}

**Note:** It is highly recommended to use the Permutation Importance technique after eliminating the highly correlated features because shuffling of one correlated feature may not find its importance as the model has access to the other similar feature. If all these correlated features are dropped from the dataset based on its least importance, then the final model may have a bad performance if one of the correlated features are highly significant.
{: .text-justify}

---