MARKETING CAMPAIGN FOR BANKING PRODUCTS

PROBLEM STATEMENT

Bank has a growing customer base. The bank wants to increase the borrower (asset customers) base to bring in more loan business and earn more through the interest on loans. So, the bank wants to convert the liability- based customers to personal loan customers. (while retaining them as depositors). The department wants to build a model that will help them identify the potential customers who have a higher probability of purchasing the loan. This will increase the success ratio while at the same time reducing the cost of the campaign. The dataset contains data on 5000 customers.
The case is that the Bank has a customer's Data with various characteristics of the customers. The management build a new product - Personal Loan and ran a small campaign towards selling the New Product to their clients. After some time, 9% of customers have a Personal Loan from The Bank.
The goal is to sell more Personal Loan products to Bank customers. To devise campaigns to better target marketing to increase the success ratio with a minimal budget. To identify the potential customers who have a higher probability of purchasing the loan. Increase the success ratio of advertising campaign while at the same time reduce the cost of the campaign.

DESCRIPTIVE ANALYSIS

Descriptive analysis is a method used in statistics and data analysis to summarize and describe the key features of a dataset. The goal is to provide a clear and concise overview of the data, helping to identify patterns, trends, and key characteristics. Descriptive analysis does not involve making inferences or drawing conclusions about a population; instead, it focuses on organizing and summarizing the available information.
![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/0f774c04-ff8a-4932-87f3-11b837cddd1e)

I could see that Experience has invalid data which is -3 value and then zip code has got 9307 which is also invalid. To add on, ID column is not going to be useful in predicting the target variable. So, this feature will have to be dropped to have dataset clean. Also, it seems like outliers are present in the following features based on the mean and max values: Experience, Income, CCAvg, Mortgage.
![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/72c0a3da-752f-42cb-9271-ff9aee0b098c)

DATA PREPROCESSING:
The process includes performing data cleaning, handling missing values, and removing outliers if necessary. Furthermore, it includes conducting data transformations, such as converting strings to numerical values, binning numerical values to categories and so on, to prepare the dataset for analysis. 

DATA CLEANING:
We removed ID Column as it is irrelevant feature for the prediction. Also, the Experience feature had around 52 negative values which were also invalid data. So, we removed them. Zip Code had invalid data containing 4 characters. So, we removed it. Also, we used one hot encoding method to categorize numbers as binary vectors.


![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/3b33d826-ddf6-4b51-ad2a-c561bb74e339)


OUTLIER DETECTION HANDLING:

Outlier detection on Income, CCavg and Mortgage:

![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/85c36fd0-be67-4a96-ac6f-aa6cdadf11ff)

EXPLORATORY DATA ANALYSIS:

We perform EDA to gain insights of the dataset. Analyze statistical properties, identify patterns, correlations, and visualize the data using descriptive and inferential statistics, data visualization techniques, and exploratory plots.
![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/f6fe8808-23e6-40e4-bd7d-75e1fa86deb9)

We must do some feature engineering on Income, CCAVg and Mortgage variables. Because if we use skewed distribution values, then it will create fault in logistic regression.

CORRELATION PLOT: 


I see that both the Experience and Age feature are highly correlated. So, I need to drop one of two have my model predict better.
![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/d8e81697-a7a4-4622-89f1-2f6466ec410e)

HANDLING IMBALANCED DATA:

We Used SMOTE Technique to handle Imbalanced data to make up for the minority class which is represents 1 in our target variable.:
![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/c29a49e7-a25b-445c-b687-83d745fb68ae)

We observed the below change in sample size after applying SMOTE Technique.
<img width="336" alt="image" src="https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/6c1f3606-925b-453f-8b27-92f67bbeea98">


TRANSFORMATION OF FEATURE VARIABLES:

We used the Yeo Johnson method of Transformation on the Income, CCavg and mortgage variable. Then, we observed the normal distribution of these variables.

DATA PREPARATION:

Then, we split the data into the train and test in the ratio of 70 and 30 ratio. After that, we applied the Standard Scaler to the dataset to standardize the input variables.
Standardization of a dataset is a common requirement for many machine learning estimators: they might behave badly if the individual features do not more or less look like standard normally distributed data (e.g. Gaussian with 0 mean and unit variance).
MODEL BUILDING:

Then, we built 4 classification models to compare and get the best model from them. Also, we used k-fold cross validation to get generalized model performance in each case. 


![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/1fe02b5c-b478-45cd-823e-bc076c4ae6bb)

ROC CURVE:

![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/f18dce00-0d32-4f98-bef2-b51ba91f4dcf)

From the above analysis, what we observe is that Both Random Forest and Decision Tree Classifier gave us the best accuracy of 99%.
The Random Forest model's ROC curve is slightly better than the Decision Tree's ROC curve as it is closer to the top-left corner of the graph. The AUC score for the Random Forest is slightly higher than that of the Decision Tree (0.9940 vs. 0.9846), indicating that the Random Forest performs slightly better in terms of distinguishing between the positive and negative classes based on the dataset.
All the four AUC scores are above 0.5, which means that all the models perform better than random guessing. 

![image](https://github.com/Sooriyavela/Bank_Loan_Modeling/assets/144498455/e10a5423-b410-4a53-a88d-94977d8dd43c)

OVERALL SUMMARY:
In the first step of this project, we imported various libraries and our data. Then we found out various things about our data.
We must make the model to predict whether a person will take a personal loan or not. We found that age and experience are highly correlated, so we dropped the experience column.ID was not a contributing factor for a person to take loan, so we dropped it. Then we used SMOTE (Synthetic Minority Over-sampling Technique) algorithm to address class imbalance.
Reason for class Imbalance: Class imbalance occurs when one class has significantly fewer samples than the other(s), leading to potential challenges in model training and biased predictions. The Income, CCAvg and the mortgage column were right skewed, so we applied Power transformation to them to normalize them.
StandardScaler to the dataset to standardize the input variables. After this we used several models to make predictions. Logistic Regression, Decision Tree Classifier, K Neighbors Classifier and Random Forest.


CONCLUSION:

Four classification algorithms were used in this project.
From the implementation, we see that both Decision tree and the Random Forest Classifier have the highest accuracy and we can choose both for our prediction.
Also, from the Exploratory data Analysis, we were able to observe that Income is the most influential feature for our prediction. Also, the weights of the features used in all the models helped us confirm this. So, “More the Income, More the possibility to get personal Loan”
Also, we observed that Customer who have more Creditcard spendings per month do have personal loan. So, it would be better for the bank to focus on customers who have got less or no Credit Spendings.

