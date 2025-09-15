# ecommercechurn

Like most e-commerce companies, this company faces a persistent retention challenge: a proportion of customers gradually disengage and stop purchasing (“churn”). Using the available data, the goal is to detect which customers are at risk of churning, so that the company can intervene proactively (e.g. giving out promos) to preserve customer relationships and revenue.

## Business Problem
Customer acquisition is costly and uncertain, while the timing of new-customer inflows is hard to predict. When existing customers churn, marketing must work harder (and spend more) to replace the dropping revenue. Although not universally true in every case, in most e-commerce settings the expected cost to retain an existing customer is lower than the fully loaded cost of acquiring a comparable new customer. The business therefore requires a scalable, reliable way to estimate churn risk at the individual level and proactively intervene to stabilize revenue.

## Goals 
1. Predict, at the customer level, the probability of churn
2. Understand important key drivers of churning


## Evaluation Metrics
We define a supervised classification task with target labels: 
* **churn** : 1
* **not churn** : 0

Confusion-matrix terms map to business outcomes as follows:
* True Positive (TP) = churners correctly identified (can be saved via intervention)
* False Positive (FP) = non-churners incorrectly flagged (unnecessary incentive risk)
* False Negative (FN) = churners missed (lost revenue and higher future acquisition burden)
* True Negative (TN) = non-churners correctly ignored (no spend).

Because missing a true churner (FN) typically carries higher economic cost than sending a cautious offer to a non-churner (FP), the evaluation will emphasize recall on the churn class (i.e., minimizing FNs), while still controlling FP. Accordingly, the primary model-selection metric is the F2 score, which weights recall more heavily than precision. But we will also report Recall and ROC AUC to provide a complete view of detection performance and model discrimination.

Below is the description of each column 
* **Tenure** : Tenure of a customer in the company
* **WarehouseToHome** : Distance between the warehouse to the customer's home
* **Number of Device Registered** : Total number of device is registered on a particular customer
* **PreferedOrderCat** : Preferred Order Category of a customer **in the last month**
* **SatisfactionScore** : Satisfactory score of a customer on service
* **MaritalStatus** : Marital status of a customer
* **NumberofAddress** : Total number of address on a particular customer
* **Complaint** : Any complaint has been raised **in the last month**
* **DaySinceLastOrder** : Day since last order by customer
* **Cashback Amount** : Average cashback in last month
* **Churn** : Churn Flag

