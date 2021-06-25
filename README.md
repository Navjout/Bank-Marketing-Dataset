# Bank-Marketing
To predict the marketing campaign outcome and to find out factors, which affect the success of the campaign. 
The classification goal is to predict if the client will subscribe to a term deposit or not.

## Marketing Introduction:
The process by which companies create value for customers and build strong customer relationships in order to capture value from customers in return. - Kotler and Armstrong (2010).

Marketing campaigns are characterized by focusing on the customer needs and their overall satisfaction. Nevertheless, there are different variables that determine whether a marketing campaign will be successful or not. There are certain variables that we need to take into consideration when making a marketing campaign.

## The 4 Ps:

1) Segment of the Population: To which segment of the population is the marketing campaign going to address and why? This aspect of the marketing campaign is extremely important since it will tell to which part of the population should most likely receive the message of the marketing campaign.

2) Distribution channel to reach the customer's place: Implementing the most effective strategy in order to get the most out of this marketing campaign. What segment of the population should we address? Which instrument should we use to get our message out? (Ex: Telephones, Radio, TV, Social Media Etc.)

3) Price: What is the best price to offer to potential clients? (In the case of the bank's marketing campaign this is not necessary since the main interest for the bank is for potential clients to open depost accounts in order to make the operative activities of the bank to keep on running.)

4) Promotional Strategy: This is the way the strategy is going to be implemented and how are potential clients going to be address. This should be the last part of the marketing campaign analysis since there has to be an indepth analysis of previous campaigns (If possible) in order to learn from previous mistakes and to determine how to make the marketing campaign much more effective.

## What is a Term Deposit?

A Term deposit is a deposit that a bank or a financial institution offers with a fixed rate (often better than just opening deposit account) in which your money will be returned back at a specific maturity time. For more information with regards to Term Deposits. 

## Machine Learning Steps Involved:
1. XGBoost

## Dataset Information  

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.

The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).  

# Steps
## Task 1 : Import Libraries
Here we will import the libraries

## Task 2 : Import Data
First of all to perform the analysis, we have to import the data:

Display first 5 rows of dataset 

## Task 3 : Data Exploration
After we imported the dataset, we have to look at the total number of rows in the dataset and analyze the number of missing values.

Bank marketing dataset consists of 4521 rows.

No missing values here.

### Task 4 : Categorical columns exploration

In the dataset we have both categorical and numerical columns. We will see values of categorical columns first.

We  will plot graph to see the data for job, marital, education, default, housing, loan, contact, month and poutcome.

### Task 5 : Numerical columns exploration
Now we will look at the numerical columns values. we will plot histograms to see the numerical values.

We will plot for balance, day, duration, campaign, pdays and previous.

We can see that numerical columns have outliers (especially 'pdays', 'campaign' and 'previous' columns). Possibly there are incorrect values (noisy data), so we should look closer at the data and decide how do we manage the noise.
We have to see closer at the values of 'campaign', 'pdays' and 'previous' columns.

Percentage of 'pdays' values above 400.

0.57509400575094
'pdays' holds the number of days that passed by after the client was last contacted from a previous campaign Looking closer into 'pdays' data we can see that.

only 1.2% of values above 400. They are possibly outliers, so we should consider imputing something (possibly mean value) instead of these values.
-1 possibly means that the client wasn't contacted before or stands for missing data.
Since we are not sure exactly what -1 means I suggest to drop this column, because -1 makes more than 50% of the values of the column.

Percentage of 'campaign' values above 20.

'campaign' holds the number of contacts performed during this campaign and for this client (numeric, includes last contact)
Numbers for 'campaign' above 34 are clearly noise, so I suggest to impute them with average campaign values while data cleaning.

Percentage of 'previous' values above 20.

'previous' holds the number of contacts performed before this campaign and for this client (numeric)
Numbers for 'previous' above 34 are also really strange, so its suggested to impute them with average campaign values while data cleaning.

### Task 6 : Analysis of the response column
It is important to look at the response column, which holds the information, which we are going to predict. In our case we should look at 'deposit' column and compare its values to other columns. 

First of all we should look at the number of 'yes' and 'no' values in the response column 'deposit'.

On the diagram we see that counts for 'yes' and 'no' values for 'deposit' are close, so we can use accuracy as a metric for a model, which predicts the campaign outcome.

Then we did the analysis for the below:
1. Deposit value counts
2. Job and deposit
3. Marital status and deposit
4. Education and deposit
5. Type of contact and deposit
6. Balance and deposit
7. Age and deposit
8. Number of contacts performed during this campaign ('campaign') and deposit.
9. number of contacts performed during previous campaign ('previous') and deposit.

Regarding the diagrams we can tell that according to our dataset:
1. Customers with 'blue-collar' and 'services' jobs are less likely to subscribe for term deposit.
2. Married customers are less likely to subscribe for term deposit.
3. Customers with 'cellular' type of contact are less likely to subscribe for term deposit.

Looking at the diagrams we can conclude that:
1. People who subscribed for term deposit tend to have greater balance and age values.
2. People who subscribed for term deposit tend to have fewer number of contacts during this campaign.

## Task 7 : Data Cleaning
Before we will be able to apply machine learning techniques, we should prepare the dataset for processing:

Convert columns with 'yes' and 'no' values to boolean columns;
Convert categorical columns into dummy variables.

## Task 8 : Machine Learning for prediction of campaign outcome

#### Classification model for the campaign outcome prediction
Now we will use cleaned datasets for prediction of campaign outcome with help of machine learning classification models. I will use __[XGBoost](https://xgboost.readthedocs.io/en/latest/)__, which is one of the most common machine learning libraries for modelling.
<br> Resulting model will also help me to understand, which features have the greatest importance for the prediction of the results of the campaing.

Create X and y datasets for training the model and split into train and test datasets.

### Get feature importance from the trained model

# Conclusion
In this project we got the categorical data for job, marital, education, default, housing, loan, contact, month and poutcome and plotted graph for better understanding. We got numerical data for balance, day, duration, campaign, pdays and previous in histogram graph for better understanding.
While analysing we concluded that:
1. People who subscribed for term deposit tend to have greater balance and age values.
2. People who subscribed for term deposit tend to have fewer number of contacts during this campaign.

We predicted the marketing campaign outcome and to find out factors, which affect the success of the campaign and if the client will subscribe to a term deposit or not.
















