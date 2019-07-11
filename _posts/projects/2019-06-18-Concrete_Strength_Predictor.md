---
layout: post
title: Concrete Compressive Strength Predictor
category: projects
---

Compressive strength is one of the characteristics of concrete, which can be described as the amount of load it can withstand before gets broken into pieces. Mathematically, it can be represented as 
{: .text-justify}
![screenshot]({{ site.baseurl }}/assets/img/comp_strength.png)
{: .text-center}

The unit of compressive strength is denoted as Pa (Pascal).
![pascal]({{ site.baseurl }}/assets/img/pascal.png)
{: .text-center}

<b>Problem Statement</b>

The compressive strength of concrete is a non-linear function, and it varies based on the ingredients it contains and the number of days it is allowed to settle. In the construction industry, before the columns and pillars are constructed, multiple concrete blocks are manufactured with different ingredients and are allowed to settle-down for varied days. Then it is subjected to destructive testing using Universal Testing Machine (UTM) to arrive at the load-bearing capacity.
{: .text-justify}

This process takes a lot of time and effort as each block has to be allowed to settle for weeks, if not months, before testing. Further, as this is the destructive testing, a significant amount of valuable resources are getting wasted. 
{: .text-justify}

<b>Solution</b> 

To save time, effort, and resources, an interactive web application is developed to predict the compressive strength of concrete block in real-time. Under the hood, this application uses a Machine Learning model (Linear Regression) trained based on the dataset extracted from the University of California - Irvine's Machine Learning repository.
{: .text-justify}

<b>Technology</b>

The extraction of data, data wrangling, exploratory data analysis, feature engineering, and machine learning (ML) model generations was done in Python using Jupyter Notebook. The Flask micro-services framework is used to wrap the final ML model to expose it as a REST API. The API, ML model, HTML templates, and other static contents are pushed into Github. Heroku PaaS server, which is wired to Github repo, is used to deploy the API and other contents to host this app.
{: .text-justify}

[Click here to look at this application in full screen](https://strength-predict-socz.herokuapp.com){:target="_blank"}. To have a quick look, see below:
{: .text-justify}

<iframe src="https://strength-predict-socz.herokuapp.com" style="border: 1; width: 800px; height: 600px"></iframe>