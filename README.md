# Instacart Grocery Basket Project Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Project Goals](#project-goals)
- [Tools and Techniques Applied](#tools-and-techniques-applied)
- [Dataset](#dataset)
- [Data Limitations](#data-limitations)
- [Key Questions](#key-questions)
- [Conclusions and Reccomendations](#conclusion-and-recommendations)

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
* Are there certain types of products that are more popular than others?
* What is the distribution among users in regards to their brand loyalty? 
* What is the frequency of Products by Price Tags?
* Are there differences in ordering habits based on a customer's region? 
* Is there a connection between age and family status in terms of ordering habits?  


## Customer Behavior - Sales Pattern

First of all, I tried to identify which days of the week were the busiest, as well as the hours of the day, since this is one of the key questions to be answered in this project. 

<p align="center">
    <img alt="Light" src="https://github.com/robcabr/Instacart_Analysis_Sales/raw/main/Visualizations/Visualizations/Customer%20Profiling/bar_orders_dow.png" width="50%">
</p>

The days are identified as follows: Saturday(0), Sunday(1), Monday(2), Tuesday(3), Wednesday(4), Thursday(5), and Friday(6).

It's possible to notice that Saturday and Sunday were the busiest days, while Wednesday and Tuesday were the least busy. 

After identifying the frequency of sales by day, it was important to identify the frequency of sales by hour, as well as the price by hour of day:


<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/Visualizations/Customer%20Profiling/hist_order_by_hour.png" width="50%">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/Visualizations/Customer%20Profiling/line_expenditure_by_hour.png" width="45%">
</p>

According to the visualization line above, prices tend to be higher between 04 AM to 08 AM and 8 PM until 10 PM. On the other hand, from 12 am to 3 am, Instacart's clients tend to spend less. 

As for the histogram, it's clear that the busiest hours are around 10 AM to 3 PM, while the least busy hours are between 12 AM to 5 AM. 

<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/Visualizations/Customer%20Profiling/hist_price_frequency_bins70.png" width="50%">
</p>

Lastly, it was created a histogram based on price by frequency, where it was possible to identify that most of the products consumed are below $15 and after this price range the consumption drops drastically. 


## Customer Profiling

After identifying the sales pattern, I started to create a profile for Instacart's Customers based on key features present in the dataset.

So, for that I tried to identify any correlation between age and other variables. 

<p align="center">
    <img alt="Light" src = "https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/Visualizations/Customer%20Profiling/scatt_age_income.png" width="50%">
    <img alt="Dark" src ="https://github.com/robcabr/Instacart_Analysis_Sales/blob/main/Visualizations/Visualizations/Customer%20Profiling/line_age_family.png" width="45%">
</p>


## Conclusion and Recommendations

Based on the finding during this project, I would recommend as follows: 
1.
2.
3.
4.
5.


What improvements could be done in this project? 

-
-
-

NOTE: This data was fabricated and used for the purposes of CareerFoundry Data Analytics - Achivement 4 (Python Fundamentals for Data Analysis). 
