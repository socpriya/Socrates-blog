---
layout: post
title: Why do Machine Learning Models deteriorate and How to address them?
category: blog
---

Most of the MOOCs, online courses, tutorials, and webinars talk about how to generate better, robust, efficient, and generic models to address business problems but not the deterioration models over a period of time and how to upkeep them so that it continues to deliver its purpose. Besides Analyzing and Generating models, a Data Scientist's role extends to Assess and Maintain them after deployment into production.

There are many reasons a model may deteriorate over a period of time. A model may start deteriorating slowly in 3 or 6 or 12 or 18 months depending upon the factors and business problem it addresses. Since there is no fixed period or template to follow, it is highly recommended to assess the model once in 3 months or at least once in 6 months.

## **<span style="color:blue">Why do models deteriorate?</span>**

Consider that there is a model developed to segment customers of an Insurance company. This model may deteriorate due to one or more reasons stated below:

**a. Added factors that are not considered originally:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The company expanded its operation to another country or added one or more product lines
	
**b. Changes in Customer Behavior:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Customers (especially millennials) expect instant insurance quotes rather than quotes emailed to them
	
**c. Changes in Business Process:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The company moved from Agent-based system to online system
	
**d. Changes in Existing factors:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The minimum wage of customers got changed but the salary of the model remains same
	
**e. Competitor:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Other competitors offer more products or process claims at faster rate that are not accounted in the model
	
**f. Changes in Industry:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Mergers and acquisition of similar companies in the industry. New start-ups that process quotes and claims through AI
	
**g. Changes in Regulations:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;New and/or updated Government regulations. Ex: mandating AML/KYC for baby-boomers and Gen-X customers 
	
**h. Changes in Product:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Change in premium rate or coverage of insurance products that makes customers to change their coverage plan
 
**h. Changes in Dataset that are not considered originally:** <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Change in discount code and/or addition of new discount code for Insurance premium calculation
 
	
## **<span style="color:blue">How to maintain models?</span>**

The following Hierarchical Processes shall be employed to maintain a model:

**1. Assess:** Assess the models periodically and proactively with new datasets and compare its performance with measures. Even if the performance deteriorates but still within the acceptable threshold, it should still be OK. However, this assessment has to be carried out at least once in 6 months.

**2. Retrain:** If the above assessment falls below the threshold, retrain the model with fresh sample of datasets - sometimes with more number of observations. However, during retraining, keep all the original and derived features of the original model. The fresh and added datasets may lead to change in coefficients of the model  performing better.

**3. Rebuild:** In spite of retrain, if the performance of model does not improve, just scrap the original model entirely and start from scratch. This means, analyzing new and old features, imputing missing values, one-hot encoding and label encoding features, performing feature engineering, building diversified models, and ensemble them. Finally deploy this model into production and perform A/B testing (aka Champion-Challenger testing) to measure the performance of new model.

---