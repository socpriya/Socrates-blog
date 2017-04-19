---
layout: post
title: Chicago Food Inspection Forecasting
category: projects
---

One of the biggest challenges _City of Chicago - Department of Public Health_ faces is, "How early a food inspector has to be sent for sanitation inspection of around 15,000 food establishments across the city, before a critical violation happens?" There are just three dozen inspectors responsible for inspecting these establishments on regular basis, amounting to ~420 establishments per person. Given the large number of inspections an inspector has to complete, the time and effort it takes to discover critical violations can mean prolonged exposure to potential disease, illness, and unsanitary conditions at some food establishments. This necessitates identifying of establishments that could likely be making a critical violation and the number of days before an inspection has to be made to those establishments.
{: .text-justify}

The data for this forecast is  taken from [The City of Chicago's GitHub location](https://github.com/Chicago/food-inspections-evaluation/tree/master/DATA). On top of the [basic models](https://github.com/Chicago/food-inspections-evaluation/tree/master/CODE) provided by them, I developed _Logitic Regression, XGBoost, Extra Trees,_ and _GBM_ predictive models, created visuals to show the performance of each model, and the number of days before an establishment has to be inspected, using ShinyApps.
{: .text-justify}

[Click here to look at this application in full screen](https://socrates.shinyapps.io/chicagofoodinspection/){:target="_blank"}. To have a quick look, scroll below:
{: .text-justify}

<iframe src="https://socrates.shinyapps.io/chicagofoodinspection/" style="border: 1; width: 900px; height: 900px"></iframe>