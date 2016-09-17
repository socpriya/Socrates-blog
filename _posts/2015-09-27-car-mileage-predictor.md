---
layout: post
title: Interactive Car Mileage Prediction
---

Most of us know that R Programming has good prediction algorithms and rich visual representation libraries available. I was wondering whether we can build an interactive Web application using R and host is online. [Shiny library](https://cran.r-project.org/web/packages/shiny/shiny.pdf), a Web Application Framework for R, came-in handy for me to achieve this. Using Shiny, developed a very simple interactive web application to predict the mileage of a car based on User's Manual. To predict that, I had to develop a Linear Regression model based on [mtcars dataset](https://stat.ethz.ch/R-manual/R-patched/library/datasets/html/mtcars.html) provided by 'Motor Trends Magazine' for various Cars, Makes, and Models, and finally hosted the application using [Shinyapps](https://www.shinyapps.io/). To determine the mileage of your car, feel free to use this interactive [Shiny application](https://socrates.shinyapps.io/CarMileagePredictor/) hosted in my Shiny site.
<br>


![screenshot]({{ site.baseurl }}/assets/img/car_mileage.png)
![screenshot]({{ site.baseurl }}/assets/img/underscore.png)