# DataScience_CS5661
Credit card fraud detection algorithm

To start with the project, open a local directory and clone:
1. Through bash - Download git-bash or direct download project zip folder.
2. Clone it through bash:
    $ git clone https://github.com/NehaDas25/DataScience_CS5661.git  
3. After cloning, open annaconda command prompt, then enter the directory of the repository.
    $ cd DataScience_5661 
4. From this directory, type jupyter notebook it should open a localhost with the repository structure as a tree.
5. Open the Credit_Card_Fraud_Detection.ipynb and start running.


<h1>Since the dataset is very huge, so the .csv file is zipped up.</h1>

<b> Visualize the data for credit card as collected: </b>
1. Unzip the credit_card.zip file and read the dataset (creditcard.csv).
2. Print the dataset. 

<b> Describe the dataset.</b>
1. The dataset looks horrible and imbalanced, so we may need to balance it.
2. Need to understand the features involved in the dataset.
3. Then proceed to balancing the dataset.

<h1> Sample the dataset and scale the features. </h1>
<b> Lets see the difference between fraud and genuine transaction.</b>

1. There are 492 fraud transactions and 284315 genuine transactions.
2. Before sampling, the contor plot looks somehow like this:

<b></b>
![This is an image](https://user-images.githubusercontent.com/100334984/159194089-0bb966b5-4c0c-4fcc-bb75-138c165429b6.png)

<b> Check whether the features are scaled or not:</b>
1. Lets use heatmap to find the correlation for the features.
2. Correlation is a table that shows relation between the feature. With heatmap and colors we can visualise and spot the difference efficiently.

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/HeatMap%20for%20correlations%20of%20features%20(V1-V28).png)


3. From the above image, we could see highest correlation between Time & V3[<-0.4], Amount & V2[<-0.4], Amount & V4[0.19].
4. Upon checking, all V - features are scaled, except Amount and Time.
5. In our project, we have used MinMaxScaler to make our work more simpler and easier.
6. There are lots of other scalers, but minmax is our best option, since we are intended to ignore intermediate values,
    rather focus on minimum and maximum values.
7. Before scaling vs After Scaling

![image](https://user-images.githubusercontent.com/100334984/159194480-235be599-8efd-4fbf-8130-d5b26af35b64.png)

8. After scaling the features Amount and Time,let us take a look at the Correlation table.

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/HeatMap%20for%20correlations%20after%20scaling%5BTime%20and%20Amount%5D.png)


<b> Lets resample dataset. </b>
1. Now that all features are scaled and everything looks fine, but dataset is still horrible.
2. We need to wipeout the difference between fraud and genuine transactions.
3. So lets choose undersampling or oversampling.
4. Well, oversampling we tried, but that has made our job more tedious and dataset becomes out of control to visualize because:
       a) Fraud cases is 492 and genuine cases is 284315.
       b) So to match up we duplicated certain values among 492 cases.
       c) And in our case, its wrong to do oversampling.
 5. So we did undersampling, by randomly selecting 492 observations from genuine transactions. That sounded very fast and proimising on visualising the dataset.
 6. After undersampling the contor plot looks something like this:

![image](https://user-images.githubusercontent.com/100334984/159194994-08532334-3118-4bf8-bbab-ecbb89e289c4.png)

<h1> Performing pre-checks on dataset for implementing algorithms.</h1>

<b> Extract the feature column and target column. </b>
1. From the normalized_data_set, class column is removed and is labelled as X.
2. We considered class column as the target from normalized_data_set and labelled as y.

<b> Split the data for X_train,X_test,y_train,y_test with test size and random state. </b>
1. Test size is taken as 0.3 and random state = 42
    
<h1> Start with implementing algorithms. </h1>

<b> KNN classifier </b>
1. k is number of neighbors you want to classify, so here k = 3.
2. Fit and predict the model, this gives y_predict.
3. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<b> Decision Tree Classifier </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<b> Random Forest classifier </b>
1. Here we will use the random state that's already used while splitting the dataset.
2. Fit and predict the model, this gives y_predict.
3. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<b> Logistic Regression </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<b> Artificial Neural Network </b>
1. We took 1 Hidden Layer with 200 neurons
2. Fit and predict the model, this gives y_predict.
3. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<b> Naive Bayes </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<b> Support Vector Machine </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test.

<h1> ROC and AUC. </h1>
<b> Finding TPR and FPR </b>

1. We calculated y_predict_probab for all the 4-algorithms. 
2. We found TPR(True Positive Rate), FPR(False Positive Rate) and Threshold for all the 4-algorithms using ROC from sklearn.

<b> Find the AUC and plotting ROC curve. </b>
1. We calculated AUC for all the 4-algorithms using metric.AUC from the FPR and TPR as caluclated in step-2.
2. Then plot the ROC curve with their respective AUC in matlib plot.

<b></b>

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/ROC.png)

<b></b>

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/ROCzoom.png)

<h1> Confusion Matrix. </h1>
<b> Plotting the Confusion Matrix for all the 7-Algorithm in two subplot </b>

1. 1st subplot containing KNN, DecisionTree, RandomForest, LogisticRegression.
2. 2nd subplot containing ANN_Algorithm, naiveBayes_algorithm, svm_algorithm.

<b></b>
    
![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Confusion%20Matrix%20for%20first%204-algorithms.png)
    
<b></b>    
 
![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Confusion%20Matrix%20for%20last%203-algorithms.png)
    
 <h> Observations from the Project </h>
 Now we have all the scores for the 7-algorithms, lets see which one gives the best among the 7-algorithms.
 Algorithms	Accuracy	Precision	Recall	ROC-AUC	F1-Score
KNN	93.58%	95.80%	91.33%	96.10%	93.51%
Decision Tree	90.54%	89.61%	92.00%	90.50%	91.80%
Random Forest	93.24%	93.91%	92.66%	97.90%	93.28%
Logistic Regression	94.59%	96.52%	92.66%	97.80%	94.55%
Artificial Neural Network	95.27%	96.57%	94.00%	97.87%	95.27%
Naïve Bayes	91.21%	97.69%	84.66%	95.50%	90.71%
Support Vector Machine	94.25%	97.84%	90.66%	97.60%	90.66%
					
![image](https://user-images.githubusercontent.com/100334984/164952744-c9f6b1a2-7d4a-41c2-a301-86f24bef5f26.png)

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Results_from_project.png)

# From the histogram above we observed that the best result was observed with ANN(Artificial Neural Network), with an accuracy of
# 95.27%, precision of 96.57%, recall of 94%, ROC of 97.87% and F1-score of 95.27%.

# So with this we conclude that for credit card fraud detection algorithm, the best suitable algorithm is ANN(Artificial Neural Network).

