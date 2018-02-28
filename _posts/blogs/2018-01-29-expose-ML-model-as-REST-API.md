---
layout: post
title: How to expose a Machine Learning Model as REST API (using Flask)?
category: blog
---

To realize the true benefit of a Machine Learning model it has to be deployed onto production environment and should start predicting outcomes for a business problem. Most of the Data Scientists know how to extract data from multiple data sources, combine, clean, and consolidate data, perform feature engineering, extract features, train multiple models, ensemble, validate, and test the models. But what they lack is, how to take a trained model onto production. 
{: .text-justify}

Well, there are multiple ways to deploy a model in production. But in this post, we will go through the process of creating a basic model and deploy it as REST API web service using Flask - a Python web framework, step-by-step. These steps are executed in Windows Operating System. But for Linux, Ubuntu, and other OS, this should work seamlessly by adopting relevant syntax.
{: .text-justify}

## **<span style="color:blue">Steps:</span>**

{: .text-justify}
1. Let us build a simple Machine Learning Model using [`iris` dataset](http://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_iris.html) that is bundled with `sklearn` package. This can be done using Jupyter Notebook, PyCharm, PyTorch or any other IDE that you are comfortable with.
<br><script src="https://gist.github.com/socratesk/383e0a0d6f448847aeb83ab712db2d61.js"></script>
Now that your machine learning model is created and persisted in hard-disk as `SVMModel.pckl`

2. In Windows _Command_ prompt, execute the below command to install Flask framework and its associated dependencies/libraries:

    `pip install flask gevent requests pillow`

3. Let us create a folder structure as below so that it can be extended to _production-like_ interactive and real-time application later.
<br>
&nbsp;&nbsp;&nbsp;![Folder]({{ site.baseurl }}/assets/img/flask-folder-struct.png)
- Root folder `flask-blog` contains server start-up class
- Sub-folder `models` contains pre-trained machine learning models
- Sub-folder `static` contains image, CSS, and JavaScript files
- Sub-folder `templates` contains static and dynamic html files

4. Under `flask-blog` folder, create a file called `server.py` with below content:
<script src="https://gist.github.com/socratesk/663e3181a59d2320a79b17c215fd2029.js"></script>

5. After the above file is created, go to `flask-blog` folder, open a _Command_ prompt, and run the command `python server.py`. It will execute as below: <br>&nbsp;&nbsp;&nbsp;![FlaskServer1]({{ site.baseurl }}/assets/img/flask-server1.png)

6. After the server is started successfully, open a browser window, and enter URL `http://127.0.0.1:5000/` <br>&nbsp;&nbsp;&nbsp;![FlaskBrowser1]({{ site.baseurl }}/assets/img/browser-1.png)
If you get a message **Hi, Welcome to Flask!!** in browser, *Congratulations*, your Flask server is up and running successfully! If you get any error or could not get the server up and running, leave a note under _Comments_ section of this blog and I will get back to you as early as possible.

7. Having successfully started the server, let us move on to extend `server.py` to predict the new observation using previously trained and stored SVM Model. <br><br>Before updating code, go to the _Command_ prompt and stop Flask server using `Ctrl-C`. Update `server.py` code as below, or may simply copy & paste the contents to your code.
<script src="https://gist.github.com/socratesk/b881a75e8ed1d7ff8c42465f0ae53b3a.js"></script>

8. Go to the _Command_ prompt again and start the server using `python server.py`. 

9. Once the server is started, open a browser window and enter the URL: <br>`http://127.0.0.1:5000/predict?sepal_length=6.0&sepal_width=2.5&petal_length=5.5&petal_width=1.6` 
&nbsp;&nbsp;&nbsp;![FlaskBrowser1]({{ site.baseurl }}/assets/img/browser-2.png)

{: .text-justify}
**Voila!** The predicted class of Iris will appear on the screen as above. Play around by changing the values of features in URLs query string.

{: .text-justify}
Now that you understood about how a machine learning model can be created, persisted onto a disk, loaded from disk, and extract features from browser request and use the model to predict, using those features.

{: .text-justify}
This application can be extended with fancy UI containing `form` element, dropdown boxes, submit button, etc..

---