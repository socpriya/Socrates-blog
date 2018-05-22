---
layout: post
title: Chicago Food Inspection Forecasting
category: projects
---

One of the biggest challenges _The City of Chicago - Department of Public Health_ faces is keeping up with the the sheer volume of food establishments across the city that require sanitation inspection. The goal is to make that inspection prior to critical health violations.
{: .text-justify}

There are just three dozen inspectors responsible for inspecting these 15,000 establishments on regular basis, amounting to ~420 establishments per person. Given the large number of inspections to be completed, the time and effort it takes to discover critical violations can mean prolonged exposure to potential disease, illness, and unsanitary conditions at some food establishments. This necessitates identifying of establishments that could likely be making a critical violation and the number of days before an inspection has to be made in those establishments.
{: .text-justify}

The data for this forecast is  taken from [The City of Chicago's GitHub location](https://github.com/Chicago/food-inspections-evaluation/tree/master/DATA). On top of the [basic models](https://github.com/Chicago/food-inspections-evaluation/tree/master/CODE) provided by them, I developed _Logitic Regression, XGBoost, Extra Trees,_ and _GBM_ predictive models. Using ShinyApps I created visuals to show the performance of each model and the number of days before an establishment has to be inspected.
{: .text-justify}

[Click here to look at this application in full screen](https://socrates.shinyapps.io/chicagofoodinspection/){:target="_blank"}. To have a quick look, scroll below:
{: .text-justify}

<iframe src="https://socrates.shinyapps.io/chicagofoodinspection/" style="border: 1; width: 900px; height: 900px"></iframe>