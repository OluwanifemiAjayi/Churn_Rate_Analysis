# Exploratory Analysis and Churn Rate Analysis of Customer Subscriptions and Transactions

## Project Outline

1. Introduction

2. Data and Libraries Importing

4. Data Assessment and Cleaning

5. Data Exploration and Visualization

6. Churn Rate Analysis

7. Conclusion

## 1. Introduction
This project aims to analyze customer subscription and transaction data, exploring the data, identifying trends, so as to understand subscription preferences across all demographics and various other metrics related to customer behavior, and also analyze the churn rate and how it changes due to different factors. The dataset includes various columns such as customer_ID, transaction_type, transaction_date, subscription_type, subscription_price, customer_gender, age_group, customer_country, and referral_type. I was able to conduct this analysis with the aid of multiple python libraries like Pandas to manipulate data, NumPy to perform numerical operations, MatPlotlib to plot data, Seaborn to plot advanced charts. The whole analysis process can be observed in full details in this [Jupyter Notebook](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/Eda%20and%20Churn%20project.ipynb)

## 2. Data and Libraries Importing
I began this project by importing the necessary libraries for data manipulation, numerical operations, data visualization and advanced date functions. The libraries used include Pandas, NumPy, MatPlotlib, and Seaborn. Additionally, I suppressed warnings for a cleaner output.
Next, I loaded the dataset into a pandas DataFrame so I could start with the analysis.

## 3. Data Assessment and Cleaning
I inspected the first 10 rows, the shape(number of rows and columns) of the dataset, the data types, and a descriptive statistical summary of the data. I converted the transaction_date column to datetime format to facilitate time-based analysis. I also transformed several columns (subscription_type, customer_gender, age_group, customer_country, referral_type) to categorical types for easier analysis. I ensured that the transaction_type column values were all in lowercase for consistency. 

## 4. Data Exploration and Visualization
I dug into the analysis of subscription preferences, customer demographics, referral effectiveness, pricing insights, transaction types, customer behaviour and geographical insights.

### Subscription Type Distribution
I counted the occurrences of each subscription type to understand their popularity.

### Average Subscription Price Change Per Year
I created a year column by extracting the year from the transaction_date column, then I calculated the average subscription price change per year for each subscription type and plotted the results using a line plot.

![Yearly_price_change_per_subscription_type](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/subscription_yearly_price_change.png)

### Subscription Preferences by Gender
I calculated the subscription counts by gender and plotted the results using a heatmap to visualize all gender's subscription preferences.

![Subscription Preferences by Gender](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/gender_subscription_type.png)

### Subscription Preferences by Country
I calculated the subscription counts by country and plotted the results using a heatmap to visualize every country's subscription preferences.

![Subscription Preferences by Country](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/country_subscription_type.png)

I continued my exploratory analysis by finding the most common country, the most effective referral method, the average price for each subscription, the most common transaction type and the average duration before changing subscription.

## 5. Churn Rate Analysis
I defined a function to determine customer status based on transaction type and created an active_or_churned column by applying this function to transaction_type, I created another function to indicate churn with a binary value(1 if a customer has churned, if otherwise then 0) and I used this function to create a churn column, I also created a churn DataFrame from my original DataFrame by filtering out every row and column for only churned customers.

I converted the churn column to numeric type, I got the unique count of customers which is the total customers count and I also calculated the total number of unique churned customers. Then I used the total customers count and total churned customers to derive the overall churn rate and analyzed the churn rate by various demographics and time periods, visualizing the results for better understanding.

### Churn Distribution
I plotted the overall distribution of the churn rate among active customers

![Churn Distribution](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_distribution.png)

### Churn Rate by Country
I calculated the churn rate for each country and plotted the distribution

![Churn Rate by Country](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_by_country.png)

### Churn Rate by Gender
I calculated the churn rate for each gender and plotted the distribution

![Churn Rate by Gender](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_by_gender.png)

### Churn Rate by Age Group
I calculated the churn rate for each country and plotted the distribution

![Churn Rate by Age Group](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_by_age_group.png)

### Churn Rate by Year
I calculated the churn rate for each country and plotted the distribution

![Churn Rate by Year](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_by_year.png)

### Churn Rate by Subscription Type
I calculated the churn rate for each country and plotted the distribution

![Churn Rate by Subscription Type](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_by_sub_type.png)

### Churn Rate by Referral Type
I calculated the churn rate for each country and plotted the distribution

![Churn Rate by Referral Type](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/churn_by_referral.png)

## 6. Conclusion
In this project, I assessed and cleaned the data, explored subscription preferences and demographics, and analyzed churn rates. The visualizations provided some valuable insights into customer behavior and subscription patterns, which can help in making informed business decisions and strategies. 

### Insights
- There is a steady increase in price for all subcription types across the three years.
- For subcription preferences across genders, male and females prefer the basic package while others prefer the pro package.
- The most common customer country is Sweden.
- Google ads is the most common referral type.
- Initial and upgrade take the most part of transaction type but reduction and churn take up a very significant percent of the whole population and this might be due to the increase in prices across the years which may prompt people to reduce their subscription type and maybe churn when they cannot afford the price.
- There is an average period of approximately 290 days before people change subscriptions and this works both ways for upgrade and reduction thereby buttressing the point above.
- Churn rate takes about 19.78% of the total population and this is a significant percentage.
- Finland is the country with the highest churn rate then it is followed by Denmark.
- Females are likely to churn more than males.
- Customers in the age group 18-24 tend to churn quickly, next is that of 25-34
- Churn rate was lowest at 2020 and highest 2022 this shows that the increase in prices acros the years is the main reason for churn.
- Those using the basic package are more likely to churn and those with max package are less likely to churn, this is because those with basic packages are mostly first time subscribers and max are returning or long time customers.
- Since google ads bring in more customers, it also has highest churn rate in all referral types.

### Recommendation strategies

- All churned customers, regardless of their demographics, should be reached out to and offerred free subscription for a period of time, this should bring a significant number of those who churned back as active customers.
- Bing, Display and Tv should be targeted for ads placements more than they are being used, although they have the lowest active customers but also their customers rarely churns.
- For all customers favouring the basic package they should be given access to pro package at basic price for a limited period this will encourage them to upgrade their subscription, the same goes for those customers favoring pro to max.
- Since google ads brings in the most customers, it should be used for running ad campaigns more.
- Most orders come from females and males therefore marketing campaigns should be done to target both genders more.
- Customer retention strategies, like permanent subscription price reduction, should be implemented to reduce churn and also prevent reduction of subscription.
- Temporary discounts can be given to also promote upgrade and retention of subcription.
- Sweden should be targeted more during ads campaigns as it is the country with the highest customer count.

## Relevant Links
- [Jupyter Notebook](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/Eda%20and%20Churn%20project.ipynb)
- [Customer Subscription and Transaction Dataset](https://github.com/OluwanifemiAjayi/Churn_Rate_Analysis/blob/main/Customer_Subscription_And_Transaction_Details.csv)
- [LinkedIn](https://www.linkedin.com/in/oluwanifemiii)
