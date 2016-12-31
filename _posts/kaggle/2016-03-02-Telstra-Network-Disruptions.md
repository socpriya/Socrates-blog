---
layout: post
title: Telstra - Prediction of Severity of Faults on Telecommunication Network
category: kaggle
---

[Telstra](https://www.telstra.com.au/) is Australia’s largest telecommunications, media, and network technology company, offering a full range of communications services. They conducted their first-ever "recruitment" competition in [Kaggle](https://www.kaggle.com/c/telstra-recruiting-network) to predict the severity of service disruptions on their network - whether it is a momentary glitch or a total interruption of connectivity. The algorithm and model developed for this competition will help Telstra to predict the severity of service disruptions and provide better service to its customers.

The competition ran from 25-Nov-2015 to 29-Feb-2016 and there were 974 individuals participated across the Globe.

The [dataset](https://www.kaggle.com/c/telstra-recruiting-network/data) comprised of multiple files each containing different features extracted from _Log files_, collected from various locations at different time. The target feature, _Fault severity_ with 3 categories _(0: No Fault, 1: Few Faults, and 2: Many Faults)_ is the one that has to be predicted from given datasets. Again, the prediction should be the probability of each severity type _(multi-class)_ for the given test dataset.

In this competition, **Multi-class logarithmic loss** was used to evaluate the performance of predicted multi-class probabilities. 

![screenshot]({{ site.baseurl }}/assets/img/MCLL-Telstra.png)

![screenshot]({{ site.baseurl }}/assets/img/underscore.png)