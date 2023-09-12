# Customer Segmentation and product recommendation

## 🏕️ Part1: Customer Segmentation: 
The the process of divide customers into groups based on same characteristic or behaviors. Business can design product or services that corresponding  of each customer behaviors’ group.

## Workshop
HDI is a networking marketing business, located in multiple countries in South East Asia. Its products are honey, propolis, royal jelly and pollen etc.

Goal: To increase HDI revenue

### 💾 Pythone Code >>>  [Code](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/code_data/Customer_Segmentation_update.ipynb)
#### Data 2021 >>>  [Load data](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/code_data/transaction_2021.parquet)
#### Data 2022 >>>  [Load data](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/code_data/transaction_2022.parquet)
#### Data 2023 >>>  [Load data](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/code_data/transaction_2023.parquet)


💠 Dataset: used in this Workshop has 4 files consisting of 
  (1) member data: customer information and membership date 590,566 records 
  (2) transaction2021 Transaction data 1,048,576 records 
  (3) transaction2022 Transaction data 995,633 records 
  (4) transaction2023 Transaction data 362,109 records

▶️ First Step: Data preperation

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/1_data_prep.png)

Because data kept in transaction form, we union all transaction file and then group data into customer single view. 

The feature we select to do clustering consisting of 

  1) Frequency: Number of times a customer purchases products within a period of 1 year.
  2) Avg. Spending: average purchase amount per time (Total amount/frequency)
  3) Avg. Discount: average discount (1-(paid amount/Total amount))
  4) Mean Time Between Purchase: Average time between purchases (last payment date-first payment date)/frequency
  5) Offline ratio: Proportion of the number of times purchased through offline channels compared to the total number of times purchased.
  6) Online ratio: Proportion of the number of times purchased through online channels compared to the total number of times purchased.

Then, transform the data for K-Means clustering by adjusting it to follow a Gaussian Distribution.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/2_Gaussian_transform.png)

▶️ 2nd Step: Clustering using Autoencoder

First, Determine the number of customer data clusters using the Elbow Method based on the chart. The appropriate number of clusters for the dataset should be divided into 4 clusters (k=4).

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/3_kmethod.png)

Then we use "Autoencoders" for clustering customers. It is an unsuperivsed Artificial Neural Network that attempts to encode the data by compressing it into the lower dimension and decoding the data to reconstruct the original input. The bottleneck layer holds the compressed representation of the input data.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/4_segmentation_result.png)

▶️ 3nd Step: Interpret the Result

Cluster 0 :  Sporadic Seekers 
sporadically seek out online shopping opportunities but don't make purchases frequently.

Cluster 1 : Discount Devotees 
highly responsive to discounts and actively seek out promotional offers, resulting in frequent purchases and
higher average spending.

Cluster 2 : Discretionary buyers 
price-sensitive and only buy when they see a good deal. They are not easily persuaded by marketing or advertising,
and they tend to have a low average spending.

Cluster 3 : Affluent Buyers 
selective in their purchasing behavior and tend to spend significantly when they do make a purchase. They have a
pattern of returning to repurchase relatively soon and enjoy the experience of shopping at offline stores.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/5_cluster_profile.png)

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/6_Customer_movement.png)

The picutre aboved show customer cluster movement over the time. 

By knowing this, it can be valuable for various businesses in several ways:
  1) Marketing Campaign Optimization: Businesses can tailor their marketing campaigns and messaging based on the shifting preferences and behaviors of different customer clusters. This ensures that marketing efforts remain relevant and effective.
  2) Product Development: Understanding how customer clusters evolve can guide product development. It helps in creating products and features that align with changing customer needs and preferences.

## 🏕️ Part2: Product Recommendation
It is a personalized marketing strategy that suggests specific products or services to individuals based on their past behaviors, preferences, and data analysis. 

## Workshop
### 💾 Pythone Code Product Recommendation >>>  [Code](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/code_data/product_recommendation.ipynb.ipynb)

#### Data (concat three years) >>>  [Load data](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/code_data/df_test.parquet)

we use the same dataset, the different is in the data preperation process, we have to prepare data in form of customer and flag each prodcut in each columns

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/7_data_for_product_recommend.png)

Two algorithm that were used are as following:

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/8_collaborative_filering.png)

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section4%3A%20Customer%20Segmentation%20%26%20Product%20Recommendation/pic/9_NMP.png)

HDI can benefit from product recommendation and customer segmentation by increasing sales through personalized product suggestions, enhancing customer engagement, and optimizing marketing efforts based on different customer preferences and behaviors. This approach fosters customer loyalty, reduces cart abandonment, and improves inventory management, ultimately leading to more effective and efficient operations and increased revenue.








     

