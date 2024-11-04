# MY-PROJECT

### Project Title:
Customers subscription analysis and insights.

---
### Project overview
This repository is about data anaylyis of a customer data subscription, subscription donation, popularity,cancellations,revenue and regional insights this analysis utilises Excel for Exploratory data analysis (EDA), SQL for query and power bi for visualization.

---
###  Table of content
Project objective
Data source
Dataset
Tools used
Data cleaning and preparation
Instructions
Data analysis
- Excel & SQl
visualization
Conclusion

---
### Project objectives
The objective of this project is to analyse customers subscription data of identity trends in subscription duration, popularity and revenue generation across different regions.
This project aim to:
- Evaluiate cancellation rate and identity
- Analyse revenue streams by subscriotion and regions
- To determine themost popular subscription types and analyse factors contributing to their success
- To provide actionable insights and recommendations to enhance customers satisfaction and optimise subcription

---
### Data source
The dataset for this project was provided as part of the class assignment which contains simulated retail sales data for analysis purposes.

---
### Dataset
- CustomerID: Unique Identifier for each customer
- SubscriptionType: Type of subscription (e.g Basic, Premium, Standard)
- SubscriptionStart: Date when the subscription started
- SubscriptionEnd: Date when the subscription ended
- Canelled: Indicates if the subscription was cancelled (TRUE/FALSE)
- Revenue: Total revenue generated from the subscription
- Region: Geagraphic region of the customer

---
### Tools Used
- Excel: For Exploratory data analysis (EDA)
- SQL: for querying data

---
### Data cleaning and preparation
The data cleaning process is crucial to ensure the integrity and reliability of the analysis.

![customer sub data set](https://github.com/user-attachments/assets/e6a62007-8abf-4416-9ad7-b3e4ac629219)

---
### Project Instructions:
1. Excel
- Calculate the average subscription duration
- Identify the most popular subscription types
- Create any other interesting reportd,

2. SQL: Write queries to extract key insightsbased on the following questions.

- retrieve the total number of customers from each region.
- find the most popular subscription type by the number of customers.
- find customers who canceled their subscription within 6 months.
- calculate the average subscription duration for all customers.
- find customers with subscriptions longer than 12 months.
- calculate total revenue by subscription type.
- find the total number of active and canceled subscriptions.

3. Power BI:
- Build a Power BI dashboard that visualizes key customer segments,
cancellations, and subscription trends. Include slicers for interactive analysis.

---
### Data analysis
### Excel
Calculate the average subscription duration:
- Average Duration: 365.35days
- Insight: The average subscription duration being around one year indicates that many customers remain subscribed for a significant period.

### Identify the most subscription types.
- The basic subscription is the clear favorite amongst customers subscribing

### create any other interesting report.

![pivot table image](https://github.com/user-attachments/assets/4f293c7f-1a09-41b6-a13a-fda6d1a22e0e)


**INSIGHTS:** The data indicates that while the east region dwemonstarte excellent customer retention with no cancellations, the North, South and the East region face challenges with high cancelation rates. The high cancellations in this region may reflect underlying issues such as; Dissatisfaction with the servic, pricing concerns or better offering from competitors. 

### SQL
Retreive the total number of customers from each region.
```SQL
SELECT Region, 
COUNT(CustomerID) AS TotalCustomers
FROM [dbo].[LITA Capstone Dataset CustomerData]
GROUP BY Region
Order by TotalCustomers desc
```
![Screenshot (66)](https://github.com/user-attachments/assets/f9b393e7-1a8a-4160-9578-14df45b4506d)
![Screenshot (90)](https://github.com/user-attachments/assets/2a5554e8-a9a9-47a4-b852-28f950f734f6)





---
- insight: The analysis of customer counts by region reveals a relativity balanced customer distribution with opportunities for growth and improvement in customer retention strategy across all areas. Focusing on understanding regional differences and enhancing customer satisfaction.

---
### Find the most popular subscription type by the number of customers.





---
### Find customers who canceled their subscription with 6months






- Observation: During the analysis period, they were no cancellations reportred among customers in the first 6montha of their subscription
- Insight: This finding indicates a strong initial engagement and satisfaction level among new subscribers, suggesting that onboarding process and early customer experiance are effective. Customer who remain engaged during the first 6months are likely to becomea loyal subscribers.

---
### Calculate the average subscrintion duration for every customers.







---
### Calculate total revenue by subscription type





---
- Insight: the major subscription type generates the highest revenue by a sustantial margin, indicating it maybe the most popylar option amongst customers. the premium and standard typetyprs generates significant less avaenue

---
###  Find the Top 3 regions by subscription cancellation







### Find the total number of active and canceled subscription









---
###  Visualization









###  Conclusion
The analysis of subscription data has provided valuable insights into customers behaviour, preferences and retention. The absense of cancelation within the first 12months reflects strong, customers satisfaction and effective boarding processes, suggesting thst customers find value in their subscriptions during this critical period. Despite the overall positive trends in cutomer retention, the analysis also revealed areas for imptovement


 






