# Predicting customer churn for a subscription-based company
In this project, I modeled subscription-based customer churn in Python, using RFM Analysis and Machine Learning classification models. This project has been executed for BoomBrush, a Dutch e-commerce site that offers a subscription for toothbrush heads.

### What is churn?
Simply put, customer churn occurs when customers stop doing business with a company. It is the estimating length of customer retention.

### Why should you care?
Customer churn is a critical metric because it gives insight into who your retained customers are and who aren’t. Trying to retain customers is much less expensive than it is to acquire new customers. Even if you have some of the best marketing campaigns in your industry, your bottom line suffers if you are losing customers at a high rate, as the cost of acquiring new customers is so high. Generally, companies spend seven times more on customer acquisition than customer retention. That is why this project will look into which customers are likely to leave us and how we can prevent customer loss.

### How to calculate? 
One of the most commonly used methods for calculating customer churn is to divide the total number of clients a company has at the beginning of a specified time period by the number of customers lost during the same period. However, in the case of the company we are researching, there is not enough time-data available to find patterns. Therefore, we use the RFM model. The RFM model stands for Recency, Frequency and Monetary Value. It segment customers based on their transactional behavior and has been proven to be an effective predictor of the customer's willingness to engage in marketing communication. 

We have defined Receny, Frequency and Monetary Value as follows:

* Recency (R): When was your last purchase?

* Frequency (F): The second most important factor is how frequently these customers purchase. The higher the frequency, the higher is the chances of these responding to the offers.

* Monetary Value (M): The third factor is the amount of money these customers have spent on purchases. Customers who have spent higher contribute more value to the business as compared to those who have spent less.

### How to predict customer churn?
Classification algorithms attempt to learn patterns in the data to be able to predict the membership of new data to one or more classes/groups. Since we are trying to predict active vs inactive customers (binary problem), there are a number of algorithms at our disposal.

* Logistic regression is a good choice for our problem.
* Another good choice is random forest.
* Support Vector Machine (SVM) is also a suitable option for this type of problem.
* Last, K-Nearest Neighbors will be used to predict active vs inactive customers.
We will create all of the above mentioned models and evaluate their accuracy afterwards

It seems that from all the models, the **RandomForest** minimizes the False Negatives the most. False Negatives are mistakes of prediciting customers that they are not going to unsubscribe (become inactive), but they actually did unsubscribe (become inactive).

Based on the accuracy scores of the test and train data (0.94 vs. 0.95 respectively), it seems the data is underfitting. This is expected, because we have few rows to train the data. To start making valid predictions, it is necessary to get more training data. Ideally there would be more data and a bigger population of high-risk customers in the complete dataset. Still, we calculated the class probabilities of the features for the random forest model.

### Next steps
We've modeled the risk of inactive customers and now have three customer segments:

1. Low - low risk of being an inactive customer (p < .3)
2. Medium - medium risk of being an inactive customer (p > 0.3 < .5)
3. High - high risk of being an inactive customer (p > 0.5)
This could feed into a dashboard to give stakeholders a glimpse of "at-risk" customers. It also provides three different groups that we can run specific actions. Some ideas:

1) Reach out to unsubscribed/inactive customers to figure out why the left.
2) Send different types of targeted emails and special offers to the high risk group. If the sample size of high risk customers is large enough, you could split off a few small treatment groups and compare how their retention and CLV change with different promotional or customer relationship strategies.
3) Determine the the highest value customers in the active customer group, and serve them additional benefits to ensure that they remain loyal customers.

Feel free to let me know if you have any issues, and thanks for checking out this repo.