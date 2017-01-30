---
layout: post
title: How significant is the "order" of libraries loaded in R?
category: blog
---


I was working on a binary Classification challenge for which I had to compute the Performance metrics for all the Predictive models. Using _XGBoost, H2O, GBM, and MLR_ packages, I developed 5 models for which AUC (ROCR) has to be computed.

Following is the order in which the libraries were loaded in the script: <br>

    library(caret)
    library(ROCR)
    library(scales) 
    library(mlr) 

For one of the models (GLMNet), I used the below code to predict Target feature:<br>
`glmNetPred <- predict(glmNetModel$glmnet.fit, ...)`

After prediction, I ran the below code to compute ROCR prediction, and it got executed successfully:<br>
`ROCRpred   <- prediction(glmNetPred, testSetActual)`

But when I executed the below code to compute Area Under Curve (AUC),<br>
`AUC        <- as.numeric(performance(ROCRpred, "auc")@y.values)`

it gave me the following error:<br>

<span style="color:red; font-family:Courier; font-size:0.75em;">
&nbsp;&nbsp;&nbsp;Error in performance(ROCRpred, "auc") :<br>
&nbsp;&nbsp;&nbsp;Assertion on 'pred' failed: Must have class 'Prediction', but has class 'prediction'.
</span> 
  
Now what? I searched for help in Net for any solution but did not find any. When I did more analysis, I found that the `ROCRpred` object was created using ROCR package's `prediction` function, and supplied to `performance` function of `mlr` package. But the `mlr` package expects the object to be of type `Prediction`.

A careful scan on the logs, when the packages were loaded, also proved the same:
  
    > library(mlr)
	
    Attaching package: ‘mlr’
    The following object is masked from 'package:ROCR':

    performance
	
What it means is that both `mlr` and `ROCR` packages contain `performance` function which is identical but have different signatures. The `performance` function in `mlr` package expects the parameter to be of type `Prediction` whereas the same function in `ROCR` package expects it to be of type `prediction` and hence is the error!!

There are two ways to solve this issue:

__a.__ Supply package name explicitly while calling the function. With this approach the _package name_ has to be specified in each and every model files and it may reduce the code readability. Further, there are chances of missing it out in some places leading to undesired results.

    ROCRpred   <- ROCR::prediction(glmNetPred, testSetActual)
    AUC        <- as.numeric(ROCR::performance(ROCRpred, "auc")@y.values)

__b.__ Load the packages in particular order. In my case the order should have been


    library(caret)
    library(mlr)
    library(scales) 
    library(ROCR) 


Since I sourced the libraries at only one place in my script for all the models, the second approach was easier for me, with which I need not specify the package name all over.


So, is it really important to load the libraries in particular order in R? Though it seems to be not in some cases, **Yes, they are important in other cases!**

---