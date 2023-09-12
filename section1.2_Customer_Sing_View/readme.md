# Customer Single View

📌
This feature integrates all relevant customer data - including their profile, transaction history, and preferences from various sources. It consolidates this data into a single row for each customer. This makes it a powerful tool for analysts and data scientists looking to understand customer behavior. By leveraging this integrated data, businesses can formulate strategies such as attracting new customers, boosting sales, or developing new products.
![test](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/1.jpg)

 [Picture Reference:](https://www.marketingweek.com/seven-step-guide-in-undertaking-a-single-customer-view-project/)

# Workshop 

📘 To better grasp this idea, we'll be using the 'supermarket' 
[dataset](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/supermarket.zip)
dataset for our workshop. The primary objective is to bolster overall supermarket sales. Our workshop can be segmented into three main parts:
1. Exploratory Data Analysis (EDA) 🤙:  to check data quality, understand data stucture and find basic insights from the dataset
2. Customer Single View 🧑: to understand customer behaviour, we group data base on 'CUST_CODE' to a single of each customer and aggregate metics like total spend, average quantity for each customer
3. Customer Segmentation 🔰: group customer based on their behaviour to provide business suggest to marketing team to increase supermarekt overall revenue.

<br>

### 💾 Pythone Code >>>  [Code](https://colab.research.google.com/drive/1WM91RQ1u2oLfDujjo1k8x0F_pfaCdVoX#scrollTo=17po5dE8Wqul)

<br>

## Part1: EDA ⛳
In this step, we will get a basic understanding of dataset struture
Check missing value, generate basic statistic, visualizations to understand the distributions and relationships in the data

🔎 The dataset has missing values consisting of: 'CUST_CODE' 85,855 rows, 'CUST_PRICE_SENSITIVITY' 85,588 rows, and 'CUST_LIFESTAGE' 144,940 rows

Since our objective 🥇 include create customer single view 'cust_code' column is essential for this, will ignore rows with missing 'cust_code' values in subsequent steps.

For EDA, let focus on the following aspect
> - Distribution of 'SPEND': How much average customer spend each basket? <br>
> - Distribution of 'QUANTITY': How many product customer typically buy? <br>
> - Popular 'SHOP_HOUR': to understand peak shopping times <br>
> - Breakdown of 'BASKET_TYPE: to see the common shopping types <br>

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/2_eda_result.png)

⛪ From the exploratory data analysis, we can derive the following insights:
- Distribution of SPEND 💸: Most of purchase are clusterd around lower end, indicate that customer tend to make a smaller purchases. These are a few larger purchases, but they are less frequent.
- Distribution of QUANTITY 🎑 : The majority of shopping ID result in the purchase of a small of items, with very few instances where a larger number of items are bought.
- Popular SHOP_HOUR ⏰: The peak shopping hours appear to be 9 PM, followed by 1-3 PM
- Breakdow of BASKET_TYPE 🧺: : 'Full Shop' is the most frequent type of shopping ID, suggesting that many customers prefer to do comprehensive shopping trips, potentially for their weekly or monthly needs. Following 'Top Up' and 'Small Shop' are also common basket types, indicating that customers also visit supermarket frequently for smaller purchases or to replenish their supplies

## Part2: Customer Single View ⛳
To prepare customer single, we will remove rows with missing 'CUST_CODE' values, group the data based on 'CUST_CODE' to get a single view of customer and aggregate metrics like total spend, average spend, total quantity, average quantity for each cusotmer

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/3_customer_single_view.png)

⚡ The customer single view has been prepared. Here are breakdown of the columns: * CUST_CODE: Unique customer code

SPEND_sum: Total amount spent by the customer <br>
SPEND_mean: Average amount spent by the customer per shopping trip <br>
QUANTITY_sum: Total quantity of items purchased by the customer <br>
QUANTITY_mean: Average quantity of items purchased by the customer per shopping trip <br>
NUM_SHOP_TRIPS: Number of shopping trips made by the cusotmer <br>


## Part3: Customer Segmentaion using K-means
In this step, we will scale the features to ensure they have equal weight dring clustering,
determine the optimal number of clustering using the Elbow method, use K-Means algorithm for customer segmentation, provide business Recommendation for each segment to increase supermarket sales

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/4_elbow_method.png)

♒The Elbow method suggests that optimal number of clusters is around 3 or 4, as the reduction in inertia starts to level off after that point. For our analysis, we will proceed with 4 clusters.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section1.2_Customer_Sing_View/pic/5_cluster_profile.png)

## Customer Cluster Profile & Recomended Strategy to incrase supermarket sales

Cluster 0: 👷 Frequent Moderate Shoppers
- Characteristic: Regular shoppers with moderate spending, but lowest spend per trip
- Suggestion strategy:
  - Offer loyalty programs discounts
  - Send personalized offers based on purchase history since they visit often

Cluster 1: 💰 High Spender
- Characteristic: Customers who spende a bit more per trip and buy more products on average, but they shop less frequntly
- Suggestion strategy:
  - Attract them with special deals to increase their shopping frequency

Cluster 2: 🤑 VIP Customer
- Characteristic: Bulk buyer or maybe they are small businesses. They have a high total spend and shop very frequently
- Suggestion strategy:
  - Offer volume-based discounts or partnerships
  - Consider a dedicated support for high-volumn customer/ VIP customer

Cluster 3: 🧑 Occasional Premium Shopper
- Characteristic: A unique customer that doesn't shop often but spend large amount of money when they do
- Suggestion strategy:
    - Analyze this group of customers' purchase behaviour in more detail to provide personalized offers
