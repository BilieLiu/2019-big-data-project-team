# 2019-big-data-project-team_taobao
# Customers Behavior Analysis of Taobao & TMall
Group member: Yuqi Liu, Weiteng Li, Shikui Wang

## 1. Summary
Online shopping is now an indispensable part of people's daily life. Customers enjoy the convinience that online shopping brings and merchants focus a lot on attracting more volume. One way is to attract more repeat customers. Our objective is to build a model that is able to identify whether a customer will become a repeat customer. We choose Taobao transaction dataset as training data. We do a lot of preprocessing and create new feature indicating whether a customer is a repeat customer. Then we utilize SparkML to build logistic regression and random forest model to see their performance. 



## 2. Introduction

The Prime Day of Amazon just passed, online shopping has been an indispensable part of people’s daily life. From customers’ stand points, online shopping is convenient, is cheaper and offers even more options. From merchants' stand point, they need to better promote their products to get more volume. To achieve the goal, they probably need to do analysis to get a better insights of their customers. Moreover, there always exists a limit for new customers, one way to attract more volume is to attract repeat customers. By targeting at customer profile that is likely to buy again, merchants can derive more revenues not just from new customers. So, our project's goal is to build up a robust machine learning model capable of identifying potential repeat customers so as to send out new promotions or new product information to those potential customers.

To build a robust model, we decided to choose Taobao transactions dataset as training data. Taobao is the biggest online shopping website in China, just like Amazon in US. This dataset contains transactions between Apr. 2015 and Dec. 2015, with over 100,000,000 transactions and columns like item id, transaction date, action(buy or not), merchant id etc. 

## 3. Code Files

## 4. Method Section

### 4.1 Cleaning and Preprocessing

The original dataset has roughly 20% missing entires. Given the dataset is large enough, we simply deleted all rows with missing values. Then, because the original dataset does not have a column indicating whether a customer is a repeat customer, we create a new columns "is_repeat” as our target column to indicate whether a customer is a repeat customer, by grouping by customer_id and merchant_id; after grouping, we utilize spark to counter each group, if a group appears more than once, this customer is a repeat customer for this merchant.
