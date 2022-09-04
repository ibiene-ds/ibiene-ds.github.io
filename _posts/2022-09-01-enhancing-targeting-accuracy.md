---
layout: post
title: Enhancing Targeting Accuracy Using ML
image: "/posts/classification-title-img.png"
tags: [Customer Targeting, Machine Learning, Classification, Python]
---
___

# Project Overview  <a name="overview-main"></a>

### Context <a name="overview-context"></a>

Our client, a grocery retailer, sent out mailers in a marketing campaign for their new *delivery club*.  This cost customers $100 per year for membership, and offered free grocery deliveries, rather than the normal cost of $10 per delivery.

For this, they sent mailers to their entire customer base (apart from a control group) but this proved expensive.  **For the next batch of communications they would like to save costs by *only* mailing customers that were likely to sign up.**

Based upon the results of the last campaign and the customer data available, we will look to understand the *probability* of customers signing up for the *delivery club*.  This would allow the client to mail a more targeted selection of customers, lowering costs, and improving ROI.

We will use different classification algorithms to take on this task!
<br>
<br>

### Results <a name="overview-results"></a>

The goal for the project was to build a model that would accurately predict the customers that would sign up for the *delivery club*.  This would allow for a much more targeted approach when running the next iteration of the campaign.  A secondary goal was to understand what the drivers for this are, so the client can get closer to the customers that need or want this service, and enhance their messaging.

Based upon these, the chosen model is the Random Forest as it was a) the most consistently performant on the test set across classication accuracy, precision, recall, and f1-score, and b) the feature importance and permutation importance allows the client an understanding of the key drivers behind *delivery club* signups. See table below for summary of all model results.

Classification Accuracy:
Precision:
Recall:
F1-score: 


As well, see the feature importances and permutation importance of the various input variables. 

<br>
**Metric 1: Classification Accuracy**

* KNN = 0.936
* Random Forest = 0.935
* Decision Tree = 0.929
* Logistic Regression = 0.866

<br>
**Metric 2: Precision**

* KNN = 1.00
* Random Forest = 0.887
* Decision Tree = 0.885
* Logistic Regression = 0.784

<br>
**Metric 3: Recall**

* Random Forest = 0.904
* Decision Tree = 0.885
* KNN = 0.762
* Logistic Regression = 0.69

<br>
**Metric 4: F1 Score**

* Random Forest = 0.895
* Decision Tree = 0.885
* KNN = 0.865
* Logistic Regression = 0.734
<br>
<br>* Logistic Regression = 0.734

___
<br>
# Application <a name="modelling-application"></a>

We now have a model object, and the required pre-processing steps to use this model for the next *delivery club* campaign.  When this is ready to launch we can aggregate the neccessary customer information and pass it through, obtaining predicted probabilities for each customer signing up.

Based upon this, we can work with the client to discuss where their budget can stretch to, and contact only the customers with a high propensity to join.  This will drastically reduce marketing costs, and result in a much improved ROI.

___
<br>
# Growth & Next Steps <a name="growth-next-steps"></a>

While predictive accuracy was relatively high - other modelling approaches could be tested, especially those somewhat similar to Random Forest, for example XGBoost, LightGBM to see if even more accuracy could be gained.

We could even look to tune the hyperparameters of the Random Forest, notably regularisation parameters such as tree depth, as well as potentially training on a higher number of Decision Trees in the Random Forest.

From a data point of view, further variables could be collected, and further feature engineering could be undertaken to ensure that we have as much useful information available for predicting customer loyalty
