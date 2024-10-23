# Credit-Card-Financial-Dashboard-using-PowerBI

## Overview
- The Credit Card Financial Dashboard is a Power BI project designed to help users analyze and visualize  credit card expenditures, track spending trends, and manage financial health.
- This interactive dashboard provides insights into spending categories, payment history, and budget tracking.


## DAX Queries 

1)  AgeGroup = SWITCH(
    TRUE(),
    'public cust_detail'[customer_age] < 30, "20-30",
    'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40",
    'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
    'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
    'public cust_detail'[customer_age] >= 60, "60+",
    "unknown"
    )


2)  IncomeGroup = SWITCH(
    TRUE(),
    'public cust_detail'[income] < 35000, "Low",
    'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med",
    'public cust_detail'[income] >= 70000, "High",
    "unknown"
    )


3) week_num2 = WEEKNUM('public cc_detail'[week_start_date])


4)  Current_week_Reveneue = CALCULATE(
    SUM('public cc_detail'[Revenue]),
    FILTER(
    ALL('public cc_detail'),
    'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])))


5) Previous_week_Reveneue = CALCULATE(
   SUM('public cc_detail'[Revenue]),
   FILTER(
   ALL('public cc_detail'),
   'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1))


## Project Insights

- Revenue increased by 28.8%
- Overall revenue is 57M
- Total interest is 8M
- Total transaction amount is 46M
- Male customers are contributing more in revenue 31M, female 26M
- Blue & Silver credit card are contributing to 93% of overall transactions
- TX, NY & CA is contributing to 68%
- Overall Activation rate is 57.5%
- Overall Delinquent rate is 6.06%

   
## Author - Suyash Ajbale
   
    
