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
Because data kept in transaction form, we union all transaction file and then group data into customer single view. The feature we select to do clustering consisting of 

--pic1--

  1) Frequency: Number of times a customer purchases products within a period of 1 year.
  2) Avg. Spending: average purchase amount per time (Total amount/frequency)
  3) Avg. Discount: average discount (1-(paid amount/Total amount))
  4) Mean Time Between Purchase: Average time between purchases (last payment date-first payment date)/frequency
  5) Offline ratio: Proportion of the number of times purchased through offline channels compared to the total number of times purchased.
  6) Online ratio: Proportion of the number of times purchased through online channels compared to the total number of times purchased.

     

