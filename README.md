# Telecom_Churn_case_study
**Business Problem Overview**
To reduce customer churn, telecom companies need to predict which customers are at high risk of churn.
In this project, I will analyse customer-level data of a telecom firm, build predictive models to identify customers at high risk of churn and identify the main indicators of churn.

**Understanding and Defining Churn**
There are two main models of payment in the telecom industry - postpaid (customers pay a monthly/annual bill after using the services) and prepaid (customers pay/recharge with a certain amount in advance and then use the services).
In the prepaid model, customers who want to switch to another network can simply stop using the services without any notice, and it is hard to know whether someone has actually churned or is simply not using the services temporarily (e.g. someone may be on a trip abroad for a month or two and then intend to resume using the services again).
Thus, churn prediction is usually more critical (and non-trivial) for prepaid customers, and the term ‘churn’ should be defined carefully.

**Definitions of Churn**
There are various ways to define churn, such as:

**Revenue-based churn**: Customers who have not utilised any revenue-generating facilities such as mobile internet, outgoing calls, SMS etc. over a given period of time. One could also use aggregate metrics such as ‘customers who have generated less than INR 4 per month in total/average/median revenue’.
The main shortcoming of this definition is that there are customers who only receive calls/SMSes from their wage-earning counterparts, i.e. they don’t generate revenue but use the services. For example, many users in rural areas only receive calls from their wage-earning siblings in urban areas.

**Usage-based churn**: Customers who have not done any usage, either incoming or outgoing - in terms of calls, internet etc. over a period of time.
A potential shortcoming of this definition is that when the customer has stopped using the services for a while, it may be too late to take any corrective actions to retain them. For e.g., if you define churn based on a ‘two-months zero usage’ period, predicting churn could be useless since by that time the customer would have already switched to another operator.

**In this project, I will use the usage-based definition to define churn.

High-value Churn: In the Indian and the southeast Asian market, approximately 80% of revenue comes from the top 20% customers (called high-value customers). Thus, if we can reduce churn of the high-value customers, we will be able to reduce significant revenue leakage.

In this project, I will define high-value customers based on a certain metric and predict churn only on high-value customers.

**Understanding the Business Objective and the Data**
The dataset contains customer-level information for a span of four consecutive months - June, July, August and September. The months are encoded as 6, 7, 8 and 9, respectively. 
The business objective is to predict the churn in the last (i.e. the ninth) month using the data (features) from the first three months. To do this task well, understanding the typical customer behaviour during churn will be helpful.
In this case, since we are working over a four-month window, the first two months are the ‘good’ phase, the third month is the ‘action’ phase, while the fourth month is the ‘churn’ phase.

**Data Preparation**
The following data preparation steps are crucial for this problem:
1. Derive new features
2. Filter high-value customers
3. Tag churners and remove attributes of the churn phase

**Modelling**
Build models to predict churn. The predictive model will serve two purposes:
It will be used to predict whether a high-value customer will churn or not, in near future (i.e. churn phase). By knowing this, the company can take action steps such as providing special plans, discounts on recharge etc.
It will be used to identify important variables that are strong predictors of churn. These variables may also indicate why customers choose to switch to other networks.

**Steps to build the model:**
1. Preprocess data (convert columns to appropriate formats, handle missing values, etc.)
2. Conduct appropriate exploratory analysis to extract useful insights (whether directly useful for business or for eventual modelling/feature engineering).
3. Derive new features.
4. Reduce the number of variables using PCA.
5. Train a variety of models, tune model hyperparameters, etc. (handle class imbalance using appropriate techniques).
6. Evaluate the models using appropriate evaluation metrics.
7. Finally, select a model based on some evaluation metric.
 
Now , build another model with the main objective of identifying important predictor attributes which help the business understand indicators of churn.
After identifying important predictors, display them visually - you can use plots, summary tables etc.
Finally, recommend strategies to manage customer churn based on observation
