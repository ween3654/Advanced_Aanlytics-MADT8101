# Customer Lifetime Value & Customer Scoring

## 📌 Introduction
In today's competitive marketplace, understanding your customer is crucial. Two key metrics that help businesses gain insights into their customers are Customer Lifetime Value (CLV) and Customer Scoring.

1. Customer Lifetime Value (CLV) 📈: Focuses on determining the overall value of a customer throughout their entire lifecycle with the business.
•	Application: Used in strategic decision-making, budget allocation for customer acquisition, and retention strategies.
2. Customer Scoring 🎯: Focuses on determining the overall value of a customer throughout their entire lifecycle with the business.
•	Application: Used in tactical day-to-day operations like marketing campaigns, customer support priority

## Use Cases: Agoda 🌐

"Agoda" is a renowned platform in the hospitality industry, connecting travelers with various accommodations. 

❗ Problem Statement
1) Despite having a robust customer base, Agoda's loyalty program, which takes the form of a points-based system for each booking made. It Consider only customer booking frequency history just one aspect.
2) This system doesn't yet capitalize on the depth of customer insights that could be drawn from their booking and travel patterns.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section2%3A%20customer%20life%20time%20value/pic/1_current_loyalty_program.PNG)

💡 Proposed Solution 
To optimize the loyalty program, Agoda can:
1.	Integrate Customer Lifetime Value (CLV) to understand the potential revenue each customer can bring over the course of their relationship with Agoda. This will help tailor special offers, discounts, and exclusive deals for high CLV customers.
2.	Implement Customer Scoring based on customer behaviors, booking patterns, and feedback. Using this score, Agoda can offer personalized travel recommendations, better deals, or even exclusive experiences based on the traveler's score.

## 📈 Part1: Customer Lifetime Value (CLV) 

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section2%3A%20customer%20life%20time%20value/pic/2_new_clv_integration.PNG)

Above picutre is concept how to calcuate Customer Lifetime Value (CLV). However, CLV can (and should) be refined by taking other factors into account, such as:
- Discount Rate: To account for the present value of future profits.
- Churn Rate: The rate at which customers stop using Agoda's services.
- Margin: To focus on profit instead of revenue. 

⚖️ An example with hypothetical numbers:
Let's assume:
APV (Average booking value on Agoda) = $200
APF (Customers book three times a year) = 3
ACL (On average, a customer uses Agoda for 5 years)

  CLV = $200*3*5 = $3,000 
 
In this simplified example, the average customer would be worth $3,000 to Agoda over their lifespan as a customer.

## What's next Step?  Take action!
 Tiered Loyalty System Based on CLV:
Divide the loyalty program into multiple tiers, with each tier being determined by a customer's estimated CLV.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section2%3A%20customer%20life%20time%20value/pic/3_new_loyalty_score.PNG)

Benefits and privileges increase as customers move up tiers. This incentivizes users to spend more to move up a tier and reap better benefits.

## 🎯 Part2:  Customer Scoring
Customer scoring is a way to rank and prioritize your customers based on specific criteria, which can be derived from their behaviors, engagement, and purchase history. It helps businesses target their marketing and customer relationship efforts more efficiently.

![](https://github.com/ween3654/Advanced_Aanlytics-MADT8101/blob/main/section2%3A%20customer%20life%20time%20value/pic/4_Customer_Scoring.PNG)

Above picture is criteria which is customer behaviour that are valueble to Agoda Platforms. 
Now, let's score a hypothetical customer:

Made 5 bookings this year = 5 x 2 = 10 points
Average booking value of $250 = 5 points
Gave two 5-star reviews = 2 x 3 = 6 points
Visits the website/app weekly = 1 point
Did not book in the last month = 0 points
Total score for the customer = 10 + 5 + 6 + 1 = 22 points

Based on this score, you might classify this customer as 'medium-value'.

Once we have scores for all customers, segment them (e.g., into high-value, medium-value, and low-value) to tailor your marketing and customer relationship efforts.

## To conclude....
How can we Utilize both CLV and customer scoring to craft personalized offers.

### 🚀 For high CLV, low scoring customers: 
  These are customers who've spent a lot but are not very engaged. They might benefit from exclusive deals or early access to new features to increase their engagement.
### 💼 For low CLV, high scoring customers: 
  These are highly engaged customers who haven't spent much. They might benefit from discounts or cash-back offers to encourage more bookings.




