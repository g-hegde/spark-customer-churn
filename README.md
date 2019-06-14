# spark-customer-churn  
Use Spark to create a predictive model of customer churn for a fictional music app called Sparkify  

### Motivation  
Churn is a problem that companies face on a regular basis. Customers may drop a service for a variety of reasons. They may find competitors better. They may find cost prohibitive. They may simply forget to renew a subscription. Whatever the reason may be, customer churn is an undesirable aspect of doing business and companies like to avoid it.  

In this project, a fictional music app called Sparkify is set up with user data. The aim in this project is to use customer data to create a predictive model of customer churn in the Spark big-data framework. If companies are able to utilize customer-usage data and find patterns in them and map them accurately to indicate which customers might churn, they could, in principle, incentivize customers to stay with them. Finding such patterns could also be useful from the perspective of targeted advertising - customers demographics with advantageous average behavior can be targeted for advertising with hopes of better returns than blanket advertising.  

### Problem statement, solution strategy and expected result  
Using Spark and associated libraries and customer data for Sparkify, a fictitious music app, create and validate a predictive model for customer churn. The strategy for solving this problem is broadly speaking as follows - Churn is defined as an existing customer cancelling a subscription. Having defined churn, differences in customer demographic (location, gender) and usage (time spent, engagement) between groups of customers that churn versus those that don't churn are explored. The a priori expectation is that some of these features will reveal a substantial difference between customers that churn versus those that don't. This information is used to create useful features for a classification model for churn. A simple model with a minimum number of features that can easily be interpreted is first attempted and is optimized for performance.  

### Performance metric  
Accuracy and F1-score. F1-score is preferred due to the imabalanced nature of the data (significantly fewer users churn than don't).  

### Summary of results  
Exploratory analysis indicated that user gender, location, account type (paid/free), total time spent on the platform and their engagement with the platform were potentially the most relevant features for machine learning. Machine learning in the Spark big-data framework was performed. Logisitc regression, Random Forest classification and Gradient Boosted classification was attempted. Random forest classification gave the best tradeoff between performance and time of execution. Parameter optimization improved results marginally.  
It was found that the location-based features could result in data-leakage and better-than-expected holdout predictive performance. Excluding location-based features resulted in a simple feature set with gender, account type, time spent, user engagement and the product of time spent and user engagement as features. Random Forest classification on this feature set gave an F1 score of nearly 93% with user engagement, time spent and their product being the dominant features explaining nearly 97% of the variance in the output.  


### Files included  
1. Sparkify.ipynb  
2. README.md (this file)  

### Libraries used  
1. pyspark.sql  
2. pyspark.ml  
3. time  
4. pandas  
5. matplotlib  
6. datetime  
7. seaborn  

### Acknowledgements  
Udacity - for providing the dataset and preparatory Spark lessons (and for making it time bound to increase accountability!)



