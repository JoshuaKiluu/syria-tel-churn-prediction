# Churn Analysis and Prediction for SyriaTel

## Overview
SyriaTel, a leading telecommunications provider, is grappling with increasing customer churn rates that threaten revenue stability and market share. This project develops a predictive churn model to identify customers at high risk of leaving, and provides actionable insights to help the company improve retention strategies.

## Objectives

Analyze historical customer data to uncover churn drivers.

Develop and evaluate predictive models to classify customers by churn risk.

Provide interpretable insights to support SyriaTel’s retention strategy.:

## Dataset
* state: the state the user lives in
* account length: the number of days the user has this account
* area code: the code of the area the user lives in
* phone number: the phone number of the user
* international plan: true if the user has the international plan, otherwise false
* voice mail plan: true if the user has the voice mail plan, otherwise false
* number vmail messages: the number of voice mail messages the user has sent
* total day minutes: total number of minutes the user has been in calls during the day
* total day calls: total number of calls the user has done during the day
* total day charge: total amount of money the user was charged by the Telecom company for calls during the day
* total eve minutes: total number of minutes the user has been in calls during the evening
* total eve calls: total number of calls the user has done during the evening
* total eve charge: total amount of money the user was charged by the Telecom company for calls during the evening
* total night minutes: total number of minutes the user has been in calls during the night
* total night calls: total number of calls the user has done during the night
* total night charge: total amount of money the user was charged by the Telecom company for calls during the night
* total intl minutes: total number of minutes the user has been in international calls
* total intl calls: total number of international calls the user has done
* total intl charge: total amount of money the user was charged by the Telecom company for international calls
* customer service calls: number of customer service calls the user has done
* churn: true if the user terminated the contract, otherwise false


## Methodology

We used the CRISP-DM framework to guide the project:

1. Business Understanding – Defined churn problem and objectives.

2. Data Understanding – Explored patterns and data distributions.

3. Data Preparation – Encoded categorical variables, feature scaling, and balanced data (SMOTE).

4. Modeling – Built and tuned multiple models (Logistic Regression, Decision Tree, Random Forest, XGBoost).

5. Evaluation – Measured performance with recall, precision, F1-score, ROC-AUC, and confusion matrices.


## Modeling Approach

Baseline Models: Logistic Regression, Decision Tree

Ensemble Models: Random Forest, XGBoost

Hyperparameter Tuning: Grid Search / Randomized Search CV

Evaluation Metrics: Focus on Recall for churn class (1) to minimize false negatives i.e. falling to identify customers who will churn.


## Key Insights

* Customers with international plans and frequent customer service calls have higher churn risk.

* Certain usage patterns (high day minutes, high total charges) correlate with churn.

* Balanced data using SMOTE significantly improved recall on the minority churn class.

## Results
Model	Accuracy	Recall (Churn)	Precision (Churn)	F1-Score (Churn)
Logistic Regression	91%	0.71	0.68	0.69
Decision Tree	93%	0.73	0.79	0.76
Random Forest	94%	0.76	0.80	0.78
XGBoost	95%	0.79	0.82	0.80y

## Model Performance Insights

* XGBoost is the best performing model overall, achieving the highest accuracy, recall, precision, and F1-score for the churn class.

* Random Forest comes in second, showing strong recall and precision with a slight drop compared to XGBoost.

* Decision Tree outperforms Logistic Regression, indicating tree-based models capture non-linear relationships better.

* Logistic Regression provides a strong baseline but lags behind tree-based methods on recall and F1-score for churn.

## Conclusion
The evaluation of four models — Logistic Regression, Decision Tree, Random Forest, and XGBoost — revealed that tree-based ensemble methods consistently outperform simpler models.

* XGBoost achieved the best overall performance, with the highest accuracy (95%), recall (0.79), precision (0.82), and F1-score (0.80) for the churn class.

* Random Forest also performed strongly, offering robust recall and precision while being slightly simpler to interpret.

* Decision Tree outperformed Logistic Regression, indicating non-linear relationships are significant in predicting churn.

* Logistic Regression remains a good baseline but lags behind in churn recall and F1-score.

## Next Steps

1. Model Deployment & Monitoring

* Deploy XGBoost as the primary churn prediction model.

* Set up A/B testing or pilot deployment to compare model predictions with real outcomes.

* Establish a monitoring dashboard to track model performance, recall, and false positive rates over time.

2. Data Enrichment & Feature Engineering

* Collect additional customer data such as tenure, payment history, complaint frequency, and interaction logs.

* Engineer new variables (usage trends, engagement scores, churn risk scores).

* Test the impact of new features on model accuracy and recall.

3. Model Optimization

* Perform threshold tuning to balance precision and recall based on business priorities.

* Experiment with stacked models or ensemble blending to maximize performance.

* Re-run hyperparameter tuning periodically as new data arrives.

4. Business Integration

* Integrate model outputs into CRM systems so retention teams can target high-risk customers.

* Design personalized retention strategies based on churn risk scores (discounts, loyalty programs, or proactive customer service outreach).

5. Continuous Improvement

* Schedule regular model retraining cycles (monthly or quarterly) to keep predictions up to date.

* Track ROI of retention campaigns triggered by the model to measure impact.

* Collect feedback from business stakeholders to refine both the model and its outputs.

## Recommendations

1. Model Deployment

* Deploy XGBoost as the primary churn prediction model.

* Keep Random Forest as an alternative where interpretability or simpler maintenance is needed.

2. Improve Recall on Churners

* Fine-tune decision thresholds to reduce false negatives.

* Continue using oversampling (SMOTE) or class weighting to handle imbalance.

3. Enhance Feature Engineering

* Create new features from customer usage patterns, complaint history, and tenure.

* Consider time-based or trend-based variables to capture evolving customer behavior.

4. Explore Advanced Techniques

* Test stacking/blending models for incremental gains.

* Build a dashboard or API to integrate churn risk scores into retention workflows.

5. Business Actionability

* Focus retention efforts on high-risk customers flagged by the model.

* Use model insights to inform targeted incentives, improve customer service, and reduce churn systematically.

