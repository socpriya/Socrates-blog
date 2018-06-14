---
layout: post
title: An interactive web application using a pre-trained Deep Learning model
category: blog
---

In one of my earlier posts, I explained about [_How to build a Web App for a Machine Learning model using Flask micro framework?_](http://blog.socratesk.com/blog/2018/01/29/expose-ML-model-as-REST-API){:target="_blank"} In this post, I am sharing a full-fledged interactive web application, developed using a pre-trained, deep learning, neural network model - [_ResNet50_](https://keras.io/applications/#resnet50){:target="_blank"}, which is trained on [ImageNet](https://en.wikipedia.org/wiki/ImageNet){:target="_blank"} dataset and bundled with [Keras](http://keras.io){:target="_blank"} library. The below table lists all the [pre-trained models](https://keras.io/applications/){:target="_blank"} bundled with Keras library. Any of these libraries can be used to build an application instantly:
{: .text-justify}


[![models]({{site.baseurl}}/assets/img/pretrained_model_comparison.png)]({{site.baseurl}}/assets/img/pretrained_model_comparison.png){:target="_blank"}
{: .text-center}

I used [Heroku](https://www.heroku.com/){:target="_blank"} - A cloud-based, _Platform as a Service_ (PaaS) provider that enables developers to build, run, and operate applications instantly. The code base used to develop this app can be found in my [GitHub location](https://github.com/socratesk/ImagePredictor){:target="_blank"}.
{: .text-justify}

**Tech stack:**

* [Keras](http://keras.io){:target="_blank"}
* [Python](http://python.org){:target="_blank"}
* [ResNet-50](https://keras.io/applications/#resnet50){:target="_blank"}
* [Flask](http://flask.pocoo.org/){:target="_blank"}
* [Heroku](http://heroku.com){:target="_blank"}
* [Gunicorn](http://gunicorn.org){:target="_blank"}
* [GitHub](http://github.com){:target="_blank"}
* JavaScript Libraries
* CSS Stylesheets

To access this [application in full screen, click here](https://imagepredictor.herokuapp.com/upload){:target="_blank"}. To have a quick look, refer below:
{: .text-justify}

<iframe src="https://imagepredictor.herokuapp.com/upload" style="border: 1; width: 800px; height: 600px"></iframe>
<br>

If you would like to know the step-by-step details of how to create an app, load the files from GitHub, build, and deploy the app in Heroku, leave a note in the _Comments_ section, by clicking [this post](http://blog.socratesk.com/blog/2018/03/30/interactive_webapp_using_pretrained_model), and I will get back to you as soon as possible.
{: .text-justify}

---