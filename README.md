# MY-PROJECT

### Project Title:
Customers subscription analysis and insights.

---
### Project overview
This repository is about data anaylyis of a customer data subscription, subscription donation, popularity,cancellations,revenue and regional insights this analysis utilises Excel for Exploratory data analysis (EDA), SQL for query and power bi for visualization.

---
###  TABLE OF CONTENTS
[Project objectives](-project-objectives)
[Data source](-data-source)
[Dataset](-dataset)
[Tools Used](-tools-used)
[Data cleaning and preparation](-data-cleaning-and-preparation)
[Project Instructions](-project-instructions)
[Data analysis](-data-analysis)
- Excel & SQl
[Visualization](-visualization)
[Recommendation](-recommendation)
[Conclusion](-conclusion)

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

```SQL
SELECT Top 1 SubscriptionType, 
COUNT(CustomerID) AS CustomerCount
FROM [dbo].[LITA Capstone Dataset CustomerData]
GROUP BY SubscriptionType
ORDER BY CustomerCount DESC
```
![Screenshot (68)](https://github.com/user-attachments/assets/bdc26c00-9b14-4903-87b2-2e5d0181e94b)

---
### Find customers who canceled their subscription with 6months
```SQL
SELECT CustomerID, CustomerName, 
DATEDIFF(Month, SubscriptionStart, SubscriptionEnd) AS DurationInMonth
FROM [dbo].[LITA Capstone Dataset CustomerData]
WHERE Canceled = '1'
  AND DATEDIFF(Month, SubscriptionStart, SubscriptionEnd) < 6
```
![Screenshot (78)](https://github.com/user-attachments/assets/b267d29e-6ebe-4d5f-8e57-d1cf8d25b7a8)
![Screenshot (77)](https://github.com/user-attachments/assets/55454b66-cb93-4692-a2df-b375ec1c5052)
- Observation: During the analysis period, they were no cancellations reportred among customers in the first 6montha of their subscription
- Insight: This finding indicates a strong initial engagement and satisfaction level among new subscribers, suggesting that onboarding process and early customer experiance are effective. Customer who remain engaged during the first 6months are likely to becomea loyal subscribers.

---
### Calculate the average subscrintion duration for every customers.

```SQL
SELECT AVG(DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd)) 
AS AverageSubscriptionDuration
FROM [dbo].[LITA Capstone Dataset CustomerData]
```
![Screenshot (70)](https://github.com/user-attachments/assets/e44eb9cf-69bd-405f-aebf-06fd616b8e42)

---
#### find customers with subscriptions longer than 12 months.
```SQL
SELECT CustomerID, CustomerName
FROM [dbo].[LITA Capstone Dataset CustomerData]
WHERE DATEDIFF(Month, SubscriptionStart, SubscriptionEnd) > 12
```
![Screenshot (79)](https://github.com/user-attachments/assets/d0bd4c36-dd14-41a7-b1ab-778d8bda6ed4)
-Observation: There were no reported cancellations among customers within the first twelve months of their subscription.
-Insight: This finding reflects a strong customer satisfaction and loyalty level during the initial year of service. The absence of cancellations indicates that the product or service effectively meets customer needs and expectations during this critical retention period

---
#### calculate total revenue by subscription type.
```SQL
SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM [dbo].[LITA Capstone Dataset CustomerData]
GROUP BY SubscriptionType
```
![Screenshot (72)](https://github.com/user-attachments/assets/fe7bce55-f6c8-4d7c-81f2-dbd9c289030c)
![Screenshot (83)](https://github.com/user-attachments/assets/f96616e8-7bae-400a-ba41-abe1d6696f10)
- Insights: The Basic subscription type generates the highest revenue by a substantial margin, indicating it may be the most popular option among customers. The Premium and Standard types generate significantly less revenue, suggesting either fewer customers or lower pricing.

---
- Insight: the major subscription type generates the highest revenue by a sustantial margin, indicating it maybe the most popylar option amongst customers. the premium and standard typetyprs generates significant less avaenue

---
###  Find the Top 3 regions by subscription cancellation
```SQL
SELECT Region, COUNT(*) AS CancellationCount
FROM [dbo].[LITA Capstone Dataset CustomerData]
WHERE Canceled = 1  
GROUP BY Region
ORDER BY CancellationCount DESC
OFFSET 0 ROWS FETCH NEXT 3 ROWS ONLY
```
![Screenshot (73)](https://github.com/user-attachments/assets/daf462eb-0ef8-42a0-9db3-5e70b2897251)
![Screenshot (82)](https://github.com/user-attachments/assets/273ff754-253b-48e5-a662-f4694e329baf)

---
### Find the total number of active and canceled subscription
```SQL
SELECT 
    SUM(CASE WHEN Canceled = 0 THEN 1 ELSE 0 END) AS ActiveSubscriptions,
    SUM(CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS CancelledSubscriptions
FROM [dbo].[LITA Capstone Dataset CustomerData]
```
![Screenshot (74)](https://github.com/user-attachments/assets/94290e2e-8cd7-4976-95f4-aeca30b251b7)
![Screenshot (81)](https://github.com/user-attachments/assets/3ee5de22-ded5-41cb-8c75-54f755fc4a98)
 Insight: There are more active subscriptions than cancelled ones, indicating a positive customer retention trend. However, the cancellation rate is still significant, warranting investigation into customer dissatisfaction.
---
###  Visualization
![Screenshot (91)](https://github.com/user-attachments/assets/8b7b173f-f61f-4e2b-91a7-ef02315440ec)

---
### Recommendation
- Enhance Customer Engagement Strategies: Continue to build on the strong customer satisfaction observed during the first twelve months by implementing regular engagement strategies. This could include personalized communication, newsletters, and updates about new features or offerings to keep customers informed and engaged.
- Implement Loyalty Programs: Develop loyalty programs that reward customers for their continued subscription. Incentives such as discounts, exclusive content, or early access to new features can motivate customers to maintain their subscriptions beyond the initial period.
- Conduct Regular Customer Feedback Surveys: Periodically gather customer feedback to identify areas for improvement. Understanding customer needs and preferences can help tailor services and address any potential issues before they lead to cancellations.
- Strengthen Onboarding Processes: Since there were no cancellations within the first year, it’s crucial to maintain the effectiveness of the onboarding process. Provide comprehensive training and resources for new subscribers to ensure they fully understand how to utilize the product or service effectively.
- Monitor Customer Behavior: Use data analytics to track customer engagement and behavior patterns. Identifying trends can help pinpoint at-risk customers and allow for timely interventions to address any issues that may arise before they lead to cancellations.
- Offer Flexible Subscription Plans: Consider introducing more flexible subscription options, such as monthly payment plans or tiered pricing models. This can attract a broader audience and make it easier for customers to find a subscription type that fits their needs and budget.
- Personalize Customer Experience: Leverage customer data to create personalized experiences. Tailoring recommendations, communication, and support based on individual customer preferences can enhance satisfaction and loyalty.
- Strengthen Support Services: Ensure that customer support is readily available and responsive. Providing multiple channels for support (e.g., chat, email, phone) can help address customer issues quickly, enhancing their overall experience.
- Utilize Case Studies and Testimonials: Share success stories and testimonials from satisfied customers to build trust and encourage new subscribers. Highlighting positive experiences can help reinforce the value of the service and attract potential customers.
- Focus on Continuous Improvement: Regularly review and update service offerings based on customer feedback and market trends. Staying responsive to changes in customer needs and preferences will help maintain high satisfaction levels and reduce the likelihood of cancellations.

###  Conclusion
The analysis of subscription data has provided valuable insights into customers behaviour, preferences and retention. The absense of cancelation within the first 12months reflects strong, customers satisfaction and effective boarding processes, suggesting thst customers find value in their subscriptions during this critical period. Despite the overall positive trends in cutomer retention, the analysis also revealed areas for imptovement.


 






