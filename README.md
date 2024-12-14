# FindDefault-Prediction-of-Credit-Card-fraud

# Problem Statement:
A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash.

It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. 

The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

We have to build a classification model to predict whether a transaction is fraudulent or not.
# DATA EXPLORATION

Dataset Overview:

1.	Feature Transformation:

    o	Numerical features reduced to 28 principal components using Principal Component Analysis (PCA).

  	o	Two untransformed features:

    	Time: Not relevant for modeling.

  		Amount: Will be scaled.

3.	Target Column:

    o	Class: Binary label:

  	   	0: Non-fraudulent

  	   	1: Fraudulent.

4.	Data Characteristics:

    o	No missing values; null-value handling is unnecessary.

    o	Imbalance Issue: Genuine transactions exceed 99%, while fraudulent ones account for only 0.17%.
________________________________________

Data Preprocessing:

1.	Scaling:
 
    o	Transform the "Amount" feature to scale values.

  	o	Drop the original "Amount" and replace it with the scaled version.

  	o	Drop the "Time" column.

3.	Data Splitting:

    o	Split data using train_test_split() with a 70-30 ratio:

       	70%: Training set.

  	   	30%: Testing set.

    o	Set a random seed to ensure reproducibility.
________________________________________

Machine Learning Implementation:

1.	Goal: Binary classification to predict fraudulent transactions.

2.	Algorithms Tested:

    o	Decision Tree: Builds straightforward "if-then-else" rules.

    o	Random Forest: Combines multiple decision trees using the "bagging" method for improved accuracy.
________________________________________

Challenges and Solutions:

1.	Class Imbalance:

    o	Models trained on imbalanced data tend to favor the majority class (genuine transactions).

    o	This can lead to poor performance in detecting the minority class (fraudulent transactions).

2.	Solution: Synthetic Minority Oversampling Technique (SMOTE):

  	o	Oversamples the minority class to balance the dataset.

    o	Results in a significant performance improvement, achieving 99%+ accuracy.
________________________________________

Performance Analysis:

   •	Random Forest outperformed Decision Tree, especially after addressing the class imbalance using SMOTE.
________________________________________

Model Deployment:
   
   •	Save the preprocessed dataset and trained model using Pickle for future deployment.

