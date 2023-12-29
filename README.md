MARKETING CAMPAIGN FOR BANKING PRODUCTS

PROBLEM STATEMENT
Bank has a growing customer base. The bank wants to increase the borrower (asset customers) base to bring in more loan business and earn more through the interest on loans. So, the bank wants to convert the liability- based customers to personal loan customers. (while retaining them as depositors). The department wants to build a model that will help them identify the potential customers who have a higher probability of purchasing the loan. This will increase the success ratio while at the same time reducing the cost of the campaign. The dataset contains data on 5000 customers.
The case is that the Bank has a customer's Data with various characteristics of the customers. The management build a new product - Personal Loan and ran a small campaign towards selling the New Product to their clients. After some time, 9% of customers have a Personal Loan from The Bank.
The goal is to sell more Personal Loan products to Bank customers. To devise campaigns to better target marketing to increase the success ratio with a minimal budget. To identify the potential customers who have a higher probability of purchasing the loan. Increase the success ratio of advertising campaign while at the same time reduce the cost of the campaign.
DESCRIPTIVE ANALYSIS
Descriptive analysis is a method used in statistics and data analysis to summarize and describe the key features of a dataset. The goal is to provide a clear and concise overview of the data, helping to identify patterns, trends, and key characteristics. Descriptive analysis does not involve making inferences or drawing conclusions about a population; instead, it focuses on organizing and summarizing the available information.

Fig 1:  Bank customer dataset

Fig. 2: Features with datatypes and missing value







Fig. 3: Features with datatypes and missing value
 
Fig. 4: Data description
By looking at the Description table in Fig.4, I could see that Experience has invalid data which is -3 value and then zip code has got 9307 which is also invalid. To add on, ID column is not going to be useful in predicting the target variable. So, this feature will have to be dropped to have dataset clean. Also, it seems like outliers are present in the following features based on the mean and max values: Experience, Income, CCAvg, Mortgage.

DATA PREPROCESSING:
The process includes performing data cleaning, handling missing values, and removing outliers if necessary. Furthermore, it includes conducting data transformations, such as converting strings to numerical values, binning numerical values to categories and so on, to prepare the dataset for analysis. 

DATA CLEANING:
We removed ID Column as it is irrelevant feature for the prediction. Also, the Experience feature had around 52 negative values which were also invalid data. So, we removed them. Zip Code had invalid data containing 4 characters. So, we removed it. Also, we used one hot encoding method to categorize numbers as binary vectors.


![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/4deac156-12af-4b5c-97bc-aa1a3775b912)

