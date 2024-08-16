# Instacart Grocery Basket Project Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Project Goals](#project-goals)
- [Tools and Techniques Applied](#tools-and-techniques-applied)
- [Dataset](#dataset)
- [Data Limitations](#data-limitations)
- [Key Questions](#key-questions)
- [Customer Behavior - Sales Pattern](#customer-behavior---sales-pattern)
- [Customer Profiling](#customer-profiling)
- [Key Observations and Recommendations](#key-observations-and-recommendations)
## Project Overview
Instacart is a popular mobile app that offers to their customers a huge variety of online grocery store for their convenience. This projects involves analyzing Instacart's 2017 sales data to uncover patters and insights of customer purchasing behaviors. The goal in this project is to offer Instacart marketing stratagies by understanding how each customer profile interact with their platform. 

## Project Goals
- Identify the busiest times and days for marketing proposes
- Determine which products are popular in each department 
- Uncover customer profiles based on purchasing behavior
- Identify if there is differences in expenditure based on the time of the day. 

## Tools and Techniques Applied
This project analysis was concluded using only Python. Through Python the following techniques were applied in the dataset selected:
- Data Cleaning and Summarizing
- Data Wrangling and Subsetting
- Data Merging
- Deriving New Variables
- Uncover Customer Profiles

Also, the following libraries were utilized:
- **Pandas** for purposes of data manipulation and analysis.
- **Numpy** for numerical operations. 
- **Seaborn** and **Matplotlib** for creating visualizations.

## Dataset
This project utilizes an open-source dataset from Instacart available at Kaggle, including sales data from 2017. The dataset can be accessed on the following link: [Kaggle](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis) on <April,24,2024>.
To ensure the data was prepared for analysis, the following steps were executed:
1. **Descriptive Analysis** - to understand dataset structure, data types, as well as summary statistics.
2. **Data Wrangling** - Dropped unnecessary columns, renamed some others for clarity, and adjusted data types 
3.**Data Consistency Checks** - Addressed inconsistencies, such as mixed data types, duplicates and missing values, to ensure data integrity
4. **Combining Data** - Merged DataFrames to create a comprehensive dataset for analysis
5. **Deriving New Variables** - Created new variables for analysis purposed and included new metrics to identify patterns. 
6. **Grouping and Aggregating Data** - Grouped data by categories and aggregated variables to uncover patters and summarize insights

## Data Limitations
While developing the present project, it was possible to notice some Data Limitations, highlighting the following ones:
1. **Temporal Scope Limitation:** This dataset includes only sales from the year of 2017, which means patterns and behaviors identified in this project may not represent the current or future trends.  
2. **Limited Product Context:** The column "products" provide limited information about product atributes. So, I had no access to additional details such as branda, promotional information, between other that could enrich the analysis or provide extra insights. 
3. **Limited Days Since Prior Order:** The column "days_since_prior" is limited at 30 days, which limit the analysis regarding long-term customer behavior and patterns, since orders that were made more than 30 days apart will receive the same value in this column. 

## Key Questions
The following questions were utilized as a guide for the present project: 

* What are the busiest days of the week and hours? 
* Is there any particular time of the day when people spend the most money?
* What is the distribution among users in regards to their brand loyalty? 
* What is the frequency of Products by Price Tags?
* Are there differences in ordering habits based on a customer's region? 
* Is there a connection between age and family status in terms of ordering habits?  


## Customer Behavior - Sales Pattern

First of all, I tried to identify which days of the week were the busiest, as well as the hours of the day, since this is one of the key questions to be answered in this project. 

<p align="center">
    <img alt="Light" src="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/bar_orders_dow.png" width="50%">
</p>

The days are identified as follows: Saturday(0), Sunday(1), Monday(2), Tuesday(3), Wednesday(4), Thursday(5), and Friday(6).

It's possible to notice that Saturday and Sunday were the busiest days, while Wednesday and Tuesday were the least busy. 

After identifying the frequency of sales by day, it was important to identify the frequency of sales by hour, as well as the price by hour of day:


<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/hist_order_by_hour.png" width="50%">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/line_expenditure_by_hour.png" width="50%">
</p>

According to the visualization line above, prices tend to be higher between 04 AM to 08 AM and 8 PM until 10 PM. On the other hand, from 12 am to 3 am, Instacart's clients tend to spend less. 

As for the histogram, it's clear that the busiest hours are around 10 AM to 3 PM, while the least busy hours are between 12 AM to 5 AM. 

<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/hist_price_frequency_bins70.png" width="50%">
</p>

Lastly, it was created a histogram based on price by frequency, where it was possible to identify that most of the products consumed are below $15 and after this price range the consumption drops drastically. 


## Customer Profiling

After identifying the sales pattern, I started to create a profile for Instacart's Customers based on key features present in the dataset.

So, for that I tried to identify any correlation between age and other variables. 

<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/scatt_age_income.png" width="50%">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/line_age_family.png" width="50%">
</p>

In both cases the analysis was unsuccessful, since:
1. It was not possible to observe any correlation between age and income, as could be observed a high flunctuation as the age increases.
2. Also, it couldn't be observed any correlation between age and number of dependants, as there is no clear pattern between these variables.

So, it was necessary to take another direction in the customer profiling.

For this, I created a profile based on the frequencdy of order placed by a customer, divided in three categories:
- Loyal Customer - Customer that has already made more than 40 orders.
- Regular Customer - Customer that has made less than 40 order but more than 10. 
- New Customer - Customer that has less than 10 orders.

<p align="center">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/bar_loyalty_brand.png" width="50%">
</p>

As can be observed, there are a higher presence of Regular Customers, followed by Loyal Customers and then New Customers. 
Although the requirements to be classified as a loyal customer require a high number of orders, the amount of regular customers it seems to far exceed the number of loyal, which could be an indicative that the majority of Instacart's orders comes from customers who have a habit of place from 10 to 40 orders per year. 

After classifying each customer by loyalty brand, I created a new variable to separate by region that each customer is located. This, way it would be possible to identify the number of customer by loyalty brand in each region of the USA. 

<p align="center">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/bar_loyalty_region.png" width="50%">
</p>

Based on the visualization above it is possible to conclude that the majority of Regular Customers and Loyal Customers, which are responsible for most of the Instacart's orders, are located in the South and West region, followed by Midwest and Northeast respectivelly.

Also, I combined the region variable with my spending flag, which use the following criteria: 
- If the customer placed 10 or more purchases, it will be considered a high spender. 
- If placed less than 10 purchases, a low spender.

<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/bar_high_spenders_region.png" width="50%">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/bar_low_spenders_region.png" width="50%">
</p>

Even after separating each region by high and low spender, it is possible to notice that the order of sales does not change, with the South and West region presenting the highest number of orders, followed by Midwest and Northeast respectivelly. 

Finally, in order to analyze whether there is any difference between consumption habits depending on family status, I generated two visualizations that reproduced the average and total order by family status.

<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/pie_sum_family_spent.png" width="50%">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/bar_avg_family_spent.png" width="50%">
</p>

According to the visualization above, no difference could be identify based on the average consumed by family status, but the total shows that Married and Single customers tend spend more than divorced/widowed and people that are currently living with parents or siblings. 

## Key Observations and Recommendations

Based on the finding during this project, I would recommend as follows: 
1. **Busiest Days and Hours**:
- **Busiest Days** - Data shows that Saturdays and Sundays have the highest frequency or orders, while Tuesday and Wednesday have the lowest order volume. Therefore, in order to optimize the reach of advertisements, it would be advisable to schedule them on Saturdays and Sundays, since these days have the highest customer traffic, while Tuesday and Wednesday would be the least advisable dates. 
- **Busiest Hours** - As for the time that these advertisements should be placed, data shouws that the peak engagement would occurs between 10 AM and 3 PM. Thus, this period would be the best to maximize user engagement. 
2. **Variation of Price** - According to the data, it was possible to notice an increase of price depending on the time of the day, as prices tend to be higher between 04 AM to 08 AM and 8 PM until 10 PM. Also, taking into consideration that Instacart's clients order tend to drop after 8 pm until it reaches the bottom between 12 AM to 5 AM, price could be one of the factors that impacts this sudden drop, so it would be advisable to consider lowering prices or offering discounts during the higher-price period could incentive customers to spend more.  
3. **Brand Loyalty Distribution** - Considering that the majority of customer demonstrate regular purchasing behavior, implementing a loyalty program offering benefits such as cashback, discounts, free delivery could enhance customer retention and even increase sales. 
4. **Regional Ordering Habits** - South and West region have higher sales compared to midwest and Northeast. Thus, it would be advisable to develop targeted advertisements based on regional customer profiles to improve sales performance across all regions. Conducting market research on each region to tailor advertisements that will attend each regional preference could be beneficial. 
5. **Family Status** - The data suggests that married and single individuals are the primary users of Instacart. Tailoring advertisements focused on this demographic could enhance effectiveness, even more for married customers, since Instacart is conveniente in supporting family needs.

NOTE: This data was fabricated and used for the purposes of CareerFoundry Data Analytics - Achivement 4 (Python Fundamentals for Data Analysis). 
