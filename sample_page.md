## Airlines Departure Delay Prediction

### Project description: 
Predicting delays helps airports and airlines plan their resources and let passengers plan their travel accurately. If we predict a delay when there is none, airports end up allocating unnecessary resources and airlines end up with dissatisfied customers who missed their flights. If we predict no delays when there is one, it can potentially result in last minute gate changes and other emergency planning for the airlines and airports.

The core questions : 
- Given all the information available prior to a flight can we accurately predict the delay? 
- Additionally, can we identify the likely causes of the delay?

For the first question, we define “delayed” as a flight that is delayed by 30 minutes or more. To answer the second part of the question, we resorted to our model implementation to give us some useful feedback.


### Challenges:
The airlines dataset is highly unbalanced with 89% of the data having no delay and only 11% of the data that is delayed by more than 30 minutes. If we run any Machine Learning algorithm on unbalanced data, it can be 89% accurate by predicting no-delay all the time. However, it is not a very useful model. 

Even if we develop a model that doesn't always predict no departure delay, there is still a major problem of bias. The model will still favor the majority class and learn features of majority class well at the expense of the minority class.

To combat this, we used SMoTe (Synthetic Minority Oversampling Technique) to balance the dataset. However, it comes with own scalability challenges. We could not make use of existing Python Smote library as the dataset has ~21 million data points in the training set and it became computationally intractable to run SMoTe on such a huge dataset. We implemented a homegrown version of SMoTe using K-nearest neighbors. However, finding K nearest neighbors would mean fitting about 2 million records in memory. We implemented a work around where we first divided the data into 1000 clusters using K-means algorithm and then applied KNN on each cluster in parallel to generate the synthetic data.

### Reports:
[1. Project Report](/pdf/Airline_Delay_Prediction.pdf) \
[2. SMOTE Implementation](/pdf/SMOTE.pdf)
