# Process-Improvement
Process improvement project to decrease personal spending and increase savings

### Impact:
 - Be able to pay for our wedding next year
 - Save money for a down payment on house to build equity
 - Stop paying monthly rent to build equity

### Goal:
 - Save $250 per week

### Success:
 - I will measure success as an increase in the weekly savings after implementing the new process
 

### Operational Definitions:
 - Weekly Spend on Food & Drink: money spent on groceries, eating at restaurants and alcohol.
 - Weekly Spend on Entertainment: money spent on events, movies, video games and other entertainment
 - Weekly Spend on Gas: money spent on gas and other car related costs
 - Weekly Spend on Shopping: money spent on personal and non-essential items
 - Weekly Spend on Other: money spent on things that are not accounted for in any of the other categories
 - Sum of Weekly Spend: sum of money spent in all categories per week

Sum of Weekly Savings: sum of money saved each week

### Defects: 
 - Overspending weekly limit of $1,100 
 - Not saving $250/week

## Process Map
This process map shows the current process I am using to save money, I will implement changes to this process to increase savings.

![image](https://user-images.githubusercontent.com/94664740/226765589-a6291870-5dd0-4231-a437-75892aae4789.png)

## Identifying the Data

### Type of Data: 
The data in this project are US dollar amounts taken from my bank statements and separated into seven categories: Food & Drink, Entertainment, Gas, Other, Shopping, Sum of Weekly Spend, Sum of Weekly Savings. 

### Data Collection: 
I collected all data by downloading and reading my online bank statements from my Chase and Wells Fargo Bank Accounts and separated the data into the 7 categories. I used the first 15 weeks of data to see the current state of spending and savings and took the last 5 weeks of data after I implemented the new process. 

### Measurement Error:
It is possible to have measurement error when classifying the data into the different categories based on bank statements. At most this would account for 1 error per week, and the sum of weekly spend and weekly savings will still be accurate.

## SQL & Sample Size

Sigma Quality Level (SQL): 
I calculated a baseline SQL for the first 15 weeks of data and will run this test again on the second sample after implementing my process improvement changes.

![image](https://user-images.githubusercontent.com/94664740/226766550-6c508ff7-32fe-4896-a3fa-3a5bd3922d4c.png)

My baseline SQL for my process was 1.4, this gives me a lot of room for improvement.

Using this formula for sample size: ![image](https://user-images.githubusercontent.com/94664740/226766630-74b36675-6ea2-4cf6-abec-18f01795de6d.png)
This gave me an N of 4.87 so I rounded to 5 samples to be able to detect a change in savings value.




















