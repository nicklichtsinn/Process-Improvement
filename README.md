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

## Correlation Analysis
I used correlation analysis to determine which input was most closely related to my spending and my savings amounts per week.
![image](https://user-images.githubusercontent.com/94664740/226766858-8d27d740-0ca9-4522-99b1-6d1d365a7bf9.png)

From this correlation matrix we can see that Shopping (0.830), Entertainment (0.775) and Food & Drink (0.702) are most closely related to spending each week.

Weekly savings are most closely related to Gas spending (-0.656), Weekly Total Spending (-0.553) and Food & Drink spending (-0.519). I am very surprised to see Gas spending be most closely related to Savings, when it does not have a strong relationship with my total weekly spend and has the lowest average spend of all the categories.

This is intuitive as I could be spending more overall when I drive places for vacation or visiting friends.

## Simple Linear Regression:
Because Shopping had the closest relationship (0.8302) with my total spend each week, I chose this input to analyze further. I used Shopping spending as the input variable using a Simple Linear Regression analysis:
![image](https://user-images.githubusercontent.com/94664740/226767062-9dc26ca2-fd87-44b1-a7e3-f32e5b42f406.png)

From this Simple Linear Regression, we see an R Squared value of 0.6621 meaning about 66.21% of the variation in overall spend per week can be explained by variation in Shopping spending. To lower spending each week to save more, it will be important to lower Shopping spending specifically each week.

## Implementing a Solution:
To reduce my Shopping spending each week I implemented some new process rules:

### No Big Purchases: 
since the main variation in my spending came from a couple large purchases I will not purchase and items over a $100 for the next 5 weeks.

### Limit Gas Spending to $30/week: 
because Gas spend had the highest negative relationship with my savings per week, I will limit myself to spending $30/week on Gas and car related things to hopefully increase my savings per week.

### Weeks 15-20:
For the last 5 weeks I have implemented these new rules and collected the data in the same method as before, pulling data from my bank statements for analysis.

## SQL & Hypothesis Test

### Sigma Quality Level (SQL): I calculated a new SQL using the last 5 weeks of data that I gathered to compare to my baseline SQL of 1.4. The new SQL for my process is 2.0, an increase of 0.6. And a decrease of 233,333 Defects per million opportunities.

![image](https://user-images.githubusercontent.com/94664740/226767839-f984fc77-7d89-4864-a3a1-625ff09bbeaa.png)

## Hypothesis Test: my previous mean for weekly spending was $811.64 and mean saving was $143.33. My new means respectively were $489.86 and $210.00. For each of these I ran a two-sample, right-tailed  (Left for Savings) hypothesis test with α = 0.05 to see if the new mean was meaningfully different from the baseline mean. Using this formula: ![image](https://user-images.githubusercontent.com/94664740/226767901-3b2e36ef-5c92-4b33-b402-066bc110d71f.png)

### Weekly Spend:
![image](https://user-images.githubusercontent.com/94664740/226767934-6f8977fc-d9e3-4d19-8a81-0cf7f60de51e.png)
For my total weekly spend, I had a Z-score of 1.39 and a P-Value of 0.1518. This was not statistically significant at the α = 0.05, and I will not reject the null hypothesis.

### Weekly Savings:
![image](https://user-images.githubusercontent.com/94664740/226768437-9bb40525-dab5-40b7-8447-965beaf6ca28.png)

For my weekly savings, I had a Z-score of -1.12 and a P-Value of 0.1313. This was not statistically significant at the α = 0.05, and I will not reject the null hypothesis.

Because both of my P-Values were not statistically significant at the α = 0.05 level I must conclude that my new means are not meaningfully different.

## Time Series & Next Steps:
Because my new means were not statistically significant, I wanted to look at an exponential smoothing time series chart for both Total Weekly Spending and Weekly Savings to anticipate future spending and saving habits.

![image](https://user-images.githubusercontent.com/94664740/226768863-a804ddbc-698b-4a93-87f6-69009e9986a2.png)

![image](https://user-images.githubusercontent.com/94664740/226768884-9ad10185-f1ed-4dbc-9a90-81204ee84501.png)

From the time series charts here we can see that spending has been below anticipated for the last 5 weeks and savings has been higher for the last 3 so my changes could be on the right track. It is possible with more weeks on this improved plan and a larger sample size I would see more significant results.

Moving forward I will have to monitor my progress to see if the trend holds and might implement new rules on spending, possibly limiting other variables in addition to gas spending to see if they have a meaningful impact on spending and saving habits.


















