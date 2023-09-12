# Churn Prediction 🏃

💢 Churn Prediciton is a data-driven process used by business to identify and predict which customers are more likely to stop using their products or services.

▶️ The primary goal of churn prediction is to proactively identify at-risk customers so that businesses can take targeted actions to prevent them from leaving. 

## Workshop: 
📘 To better grasp this idea, we'll be using the 'supermarket' 
[dataset](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/supermarket.zip)

<br>
### 💾 Pythone Code >>>  [Code](https://colab.research.google.com/drive/13SrcVFWZ2egVO7UCeqxs7cj-xio5XDQY#scrollTo=XDiBgQs7Yv_h)
<br>
<br>


There are mainly two steps to do this:

### Step 1: Lable Churn Customer

⏰ Determine a time window to label customer as churned. Let's use a 30-day window for our analysis, which mean a customer hasn't shopped in the last 30 days from their last shopping date, we will label them as churned

To label churn customer, First, for each customer, find the difference in days between their consecutive. Next, if the maximum difference for a customer exceeds 30 days, we will label them as churn (1). Otherwise, they're not churned (0)

👀 Now, we have successfully labeled the customers based on our 30-day window. A label of '1' indicates that customer has churned 😖. It contains 2,122 customers. While '0' means they havn't churned 🙂, contains 1,317 customers


### Step2: Build a churn prediction model
we need to: 
- Feature Engineering
- Data Spliting
- Model Traning/ evaluation

We need to preparation as a customer single view, 1 customer 1 row. For feature engineering, we can consider the following features:

- Total spend by a customer
- Average spend by a customer
- Total quantity of products purchased
- Number of shopping trips
- Last shopping date

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section3%3A%20Churn%20Prediciton/pic/1_customer_single_view.png)

Before we train model, we adjusted imbalanced data by undersampling data. The total data before train model contains 2,634 customers which contains class (1: Churn) and (0: not Churn) 1,317 each equally.

Next, we split data for train model 80% and test 20%. For the classifier, we chose to start with a simple model like Logistic Regression. The result of are...
- Macro Average Precision: 53%
- Macro Average Recall: 52%
- Macro Average F1-Score: 50%

From the result, this means the model correctly predicted the class for 52% of the instances. There are still gap for improvement the model. 

### 💐 Based on this model, what factors influence churn behaviour?


![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section3%3A%20Churn%20Prediciton/pic/2_feature_important.png)

From the plot and the table, we can make the following observations regarding feature importance:

  1. Average Spend (AVG_SPEND): This is the most influential feature. A negative coefficient means that as the average spend increases, the likelihood of a customer churning decreases. This suggests that customers who spend more on average are less likely to churn.
  2. Total Spend (TOTAL_SPEND): This has a positive coefficient, suggesting that as the total spend of a customer increases, the likelihood of churn also increases. This might seem counterintuitive given the average spend's negative influence. It could be that some customers who made significant purchases in the past but have reduced their spending recently are more likely to churn. This needs further investigation.
  3. Total Quantity (TOTAL_QUANTITY) and Number of Trips (NUM_TRIPS): Both features have negative coefficients, indicating that as these values increase, the likelihood of churn decreases. Customers who buy more items or visit the store more frequently are less likely to churn

☑️ Suggested Strategies:
  1. Focus on Customer Spending:
Encourage customers to spend more by offering loyalty programs, discounts, or personalized offers. Since average spend is a significant predictor, increasing the average transaction value can reduce the chances of churn.
  2. Engage with High Total Spenders:
Identify customers with high total spend but decreasing average spend. Engage with them through personalized communication or offers to understand and address any concerns or changing needs.
  3. Frequent Shopper Programs:
Implement programs or offers that incentivize frequent visits. Customers who visit more frequently are less likely to churn. Consider loyalty cards, point systems, or exclusive deals for regular shoppers.


🐤 Room for improvment the accuracy of the model
We can improve by 
- Revising features that indicate the likelyhood of customer churn
- Consider other solution to handle imbalanced data, including of oversampline or SMOTE
- Try other classification algorithms, such as, SVM, random forest... etc. (In this example, we use just one model)
  




