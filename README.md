﻿# Income-Analysis-Netflix-Mattel-Coca-cola-Booking.com
## Task: To compare the income metrics of four well known companies working in different industries and find out how the Covid crisis affected their incomes and their recovery afterwords.
DATA: The data was pulled vie API provided by Alpha Vantage: Income Statements os stock symbol: KA, MAT, NFLX and BKNG

# Part 1: My original idea was to just analyse the income of Mattel and check if the Barbie movie had affected the Net Income and what was the idea behind creating the movie
## pulling the data from alpha vantage, file: income_statement_barbie.csv
* libraries: request, datetime, pandas, dotenv, os
* created an .env file for the api key and the url provided by the website
* created a .gitigone file so I do no push my  cridentials
* I used a function to fetch and save the income statement, using the key words required by the website: symbol, finction and apikey
* checking if the request was successful with checking the status_code
* extracting the time series data (because the website works with Json)
* covert the time series to padna dataframe
* check the original columns for debugging
* rename the columns
* ensuring columns exist before converiosn with an if clause
## EDA: file: mattel_Income_Analysis.ipynb
* libraries: numpy, pandas, matplotlib, matplotlib.pyplot, seaborn
* the file consists of just 15 rows so it was not necessary to do the cleaning, check for duplicates, so i started right away plotting to see what was going on
* Line Chart of Total Revenue and Net Income Over Time
* Bar Chart of Gross Profit, Operating Income, and Net Income
* Stacked Bar Chart of Cost of Revenue, SG&A, R&D, and Operating Expenses
* I quicky realize the data was not enough for me the create a very informative analysis and came up with the idea to create a comparios betweeen several companie
* Originally I wanted to add Disney, Netlix and Mattel but Disneys income documentation was very incomplete: file: income_statement_disney.csv
* After considering several options I have decided the compare incomes from different industries and see how in general they are performing and was there a huge impact on their income after Covid-19
* I have pulled the data from Aplha Vanatage for all the companies using the same method, files: netflix_income_api.py, disney_income_api.py, booking_income_api.py, cola_income_api.py
## Data preparation, file: Income_data_preparation.ipynb
* libraries: pandas, numpy
* First I checked how all dfs looked like using head and .columns
* Created a function which transforms the Fiscal date to datetime and then extracts the year in another column (applied to all)
* Dopped unnecessary columns which I did not need for my dashboard: Fiscal Date Ending', 'Reported Currency', 'Net Interest Income', 'Interest Income',
       'Interest Expense', 'Non-Interest Income', 'Other Non-Operating Income','Interest and Debt Expense',  'Comprehensive Income Net of Tax', 'EBIT', 'EBITDA',
       'Net Income from Continuing Operations',
       'Depreciation', 'Depreciation and Amortization'
* Added company as a new column to all dfs and filled with the company name
* Used concat for combinig the dfs because they have the same columns
* Saved as an excel file
## Preparation of the Dashbaorad:
* Used Tableau for the charts and canva for the design
* Created a line chart comparing the different metrics
* Created four donut charts showing Net Income to Tax Expense for each company
* Created Percentage Difference from Previous Year with arrows which can be filltered per Metric
* Created a Bar chart which compares the money spent for Research per company (unfortunately, the data was empty for some of the companies but it was still insightful)
# link to the dashboard: https://public.tableau.com/app/profile/gabriela.arlt/viz/TheGiants_Income_Analysis/IncomeAnalysis
## Some Interesting Findings:
* Booking as a travel ecommerce company sufffered the most 2020, the crisis hit them a lot but they started recovering quick afterwords
* Mattel has the lowset revenue from all three companies which was very surprising to me, additionally the company was not drastically affected by COVID-19, eventhough I was expecting that people would start buying more toys for their children because they were not able to attend daycare
* Netflilx is having a very stable growth during the years and they invest a lot in reserach and have a very low Tax Expense compared to the other companies
* Coca-cola was the oldest company and in the beverage sector has the highest revenue (double from the other companies)
* The Income Tax expense was drastically increased 2017 for all companies but Netflix, I will guestt that there were some regulatory changes















Result and Final EDA was created with Tableau: 
 https://public.tableau.com/app/profile/gabriela.arlt/viz/TheGiants_Income_Analysis/IncomeAnalysis
