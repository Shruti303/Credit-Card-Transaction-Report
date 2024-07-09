# Credit-Card-Transaction-Report


Power BI Dashboard# 1

Project Objective:To construct a comprehensive weekly dashboard for credit cards that delivers real-time insights into critical performance metrics and trends, empowering stakeholders to efficiently monitor and analyze credit card operations
.
Importing Data To SQL database : a) Prepare csv file b) Create tables in SQL c) Import csv files into SQL

Used Dax Queries for : 

a)  Age Grouping= SWITCH(

TRUE(),

'PROJECT (CUSTOMER CREDIT)'[customer_age] < 30, "20-30",''PROJECT (CUSTOMER CREDIT)'[customer_age] >= 30 && 'PROJECT (CUSTOMER CREDIT)'[customer_age] < 40, "30-40",

'PROJECT (CUSTOMER CREDIT)'[customer_age] >= 40 && 'PROJECT (CUSTOMER CREDIT)'[customer_age] < 50, "40-50",

'PROJECT (CUSTOMER CREDIT)'[customer_age]>= 50 && 'PROJECT (CUSTOMER CREDIT)'[customer_age]< 60, "50-60",

'PROJECT (CUSTOMER CREDIT)'[customer_age]>= 60, "60+",

"unknown")


b)  Income Grouping=SWITCH (

TRUE(),

'PROJECT (CUSTOMER CREDIT)'[income] < 35000, "Low",

'PROJECT (CUSTOMER CREDIT)'[income] >= 35000 && 'PROJECT (CUSTOMER CREDIT)'[income] <70000, "Med",

'PROJECT (CUSTOMER CREDIT)'[income] >= 70000, "High",

"unknown")


c)  Revenue Earned ='Project-1(credit card)'[annual_fees] + 'Project-1(credit card)'[total_trans_amt] + 'Project-1(credit card)'[interest_earned]


d)  week_num2= WEEKNUM('Project-1(credit card)'[week_start_date])


e)  Curent week revenue= = CALCULATE(

SUM('Project-1(credit card)'[Revenue]),

FILTER(

ALL('Project-1(credit card)'),

'Project-1(credit card)'[week_num2] = MAX('Project-1(credit card)'[week_num2]))) 


f)  Previous week Revenue  = CALCULATE(

SUM('Project-1(credit card)'[Revenue]),

FILTER(

ALL('Project-1(credit card)'),

'Project-1(credit card)'[week_num2] = MAX('Project-1(credit card)'[week_num2])-1))

Project Visualization :  a) credit card transaction    b) credit card customer transactio report

Project Insights=

• Overall revenue is 57M

• Total interest is 8M

• Total transaction amount is 46M
• Male customers are contributing more in revenue 31M, female 26M
• Blue & Silver credit card are contributing to 93% of overall transactions
• TX, NY & CA is contributing to 68%
• Overall Activation rate is 57.5%
• Overall Delinquent rate is 6.06%

