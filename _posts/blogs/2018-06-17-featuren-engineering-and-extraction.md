---
layout: post
title:  Feature Engineering, Feature Extraction, and Feature Selection
category: blog
keywords: Feature selection, feature extraction, feature engineering
---
To improve the performance of a Machine Learning (ML) model, *Feature Engineering, Feature Extraction,* and *[Feature Selection](http://blog.socratesk.com/blog/2018/02/24/feature_importance_and_identification){:target="_blank"}* are the important aspects, besides *Model Ensembling* and *Parameter Tuning*. Data Scientists spend most of their time working on features than on developing ML models. This post, which contains examples and corresponding Python code, is aimed towards reducing the time spent on handling features.
{: .text-justify}

***Feature Engineering*** is more of an art than science that requires domain expertise. It is a process through which new features are created, though the original dataset could have been used as such. The new features help arrive at better ML model than the one trained from the original dataset. Most of the time, the new features help improve the accuracy of a model and help [minimize the cost function](https://en.wikipedia.org/wiki/Loss_function){:target="_blank"}.
{: .text-justify}

![models]({{site.baseurl}}/assets/img/feature-engg.png)
<script src="https://gist.github.com/socratesk/438c9a98a5a2cea09a60388be26c3c14.js"></script>
	
<br>
In ***Feature Extraction***, the existing features are converted and/or transformed from raw form to most useful ones so that the ML algorithm can handle them in a better way.  Let us dive into some of the frequently used feature engineering techniques that are widely adopted across the industry on the Categorical features.
{: .text-justify}

**A. Categorical Features:**

1. **One-hot Encoding:** Represent each categorical variable as a binary vector
>
	![models]({{site.baseurl}}/assets/img/one-hot-encode.png)
	<script src="https://gist.github.com/socratesk/ee0ffea1ee88d38b712dcd39868eabd9.js"></script>
	
2. **Label Encoding:** Assign each categorical variable (label) a unique numerical ID
>
	![models]({{site.baseurl}}/assets/img/label-encode.png)
	<script src="https://gist.github.com/socratesk/f8d7228d259acb3d82b07256ba475330.js"></script>

3. **Label Count Encoding:** Replace categorical variables (labels) with their total count
>
	![models]({{site.baseurl}}/assets/img/count-encode.png)
	<script src="https://gist.github.com/socratesk/c7c170924c571187df74df2d521ed848.js"></script>
		
4. **Label Rank Encoding:** Rank categorical variables (labels) by their count (more count higher number)
>
	![models]({{site.baseurl}}/assets/img/label-count-encode.png)
	<script src="https://gist.github.com/socratesk/23be733017f6d6adc721f00842d47b56.js"></script>
		
5. **Target Encoding:** Encode categorical variables by their ratio of target (label)
>
	![models]({{site.baseurl}}/assets/img/target-encode.png)
	<script src="https://gist.github.com/socratesk/33c61fdf48a23c838545273ffb4f98d2.js"></script>

6. **NaN Encoding:** Assign explicit encoding to NaN values in a category
>
	![models]({{site.baseurl}}/assets/img/nan-encode.png)
	<script src="https://gist.github.com/socratesk/1a2c6c71c7be0d814094b15641ca0c0f.js"></script>
	
7. **Expansion Encoding:** Create multiple categorical variables from a single variable
>
	![models]({{site.baseurl}}/assets/img/expansion-encode.png)
	<script src="https://gist.github.com/socratesk/d7975a159b2038a5d9e70fe343bdc829.js"></script>
	
8. **Consolidation Encoding:** Map different categorical variables to the same variable
>
	![models]({{site.baseurl}}/assets/img/consolidation-encode.png)
	There are no fixed ways to perform consolidation encoding. It purely depends on the type of data provided. However, [Regular Expressions (regex)](https://en.wikipedia.org/wiki/Regular_expression){:target="_blank"}, String parsing, [Stemming](https://en.wikipedia.org/wiki/Stemming){:target="_blank"}, [Lemmatisation](https://en.wikipedia.org/wiki/Lemmatisation){:target="_blank"}, [Stop words](https://en.wikipedia.org/wiki/Stop_words){:target="_blank"} and other techniques used for [Natural Language Processing (NLP)](https://en.wikipedia.org/wiki/Natural_language_processing){:target="_blank"} can be employed to consolidate the data.
	{: .text-justify}
	
**B. Numerical Features:**

Performing feature engineering on numerical data is different from that on categorical data. In numerical data, the techniques involve *rounding, binning, scaling, missing values imputation, the interaction between features*, etc.
{: .text-justify}

<br>
***Feature Selection*** helps identify the most significant features, from a given dataset, which will be helpful in generating a better model. Besides the raw dataset, a Data Scientist has to use the engineered and extracted datasets as well to identify the importance of them. For example, to predict whether a startup company will be profitable or not, the Administrative expense may not be a significant feature when compared to Marketing and R&D expenses. To determine this, follow the article ["How to identify the features that are important for a Machine Learning model?"](http://blog.socratesk.com/blog/2018/02/24/feature_importance_and_identification){:target="_blank"} that explains how features can be selected using statistically and through the ML model.
{: .text-justify}
---