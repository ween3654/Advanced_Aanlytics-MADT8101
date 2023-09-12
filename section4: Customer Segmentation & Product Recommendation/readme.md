# Customer Segmentation and product recommendation

## 🏕️ Part1: Customer Segmentation: 
The the process of divide customers into groups based on same characteristic or behaviors. Business can design product or services that corresponding  of each customer behaviors’ group.

## Workshop
HDI is a networking marketing business, located in multiple countries in South East Asia. Its products are honey, propolis, royal jelly and pollen etc.

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

--pic5--



     

