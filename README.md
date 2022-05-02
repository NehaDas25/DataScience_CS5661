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
 5. So we did Random undersampling, by randomly selecting 492 observations from genuine transactions. That sounded very fast and proimising on visualising the dataset.
 6. After undersampling the contor plot looks something like this:

![image](https://user-images.githubusercontent.com/100334984/159194994-08532334-3118-4bf8-bbab-ecbb89e289c4.png)

 
 7. Next we performed the 2nd Undersampling Technique called NearMiss Undersampling. In NearMiss UnderSampling technique, there are three version but for this    project version 2 is used. In simplest term, the method will balance the dataset by looking at the class distribution and removing samples from Majority Class randomly.
 8. Using the vesion 2 of NearMiss,the dataset will be balanced by calculating the average minimum distance between the Majority class and 3 (N furthest samples) of the minority class and selects the smallest.
 9. To perform NearMiss we simply import NearMiss from the imblearn library, we then initialize NearMiss using version 2 and perform fit_resample to both the Features and the Target.
 10. Below is the Scatter plot for " Before NearMiss Undersampling ".


![image](https://user-images.githubusercontent.com/100334984/166180557-e83995a9-77ef-4c84-8c46-b09a158d499d.png)


 11. Below is the scatter plot for " After NearMiss Undersampling ".
 
 
 ![image](https://user-images.githubusercontent.com/100334984/166180965-fe9e0312-8cf3-408e-acae-a2e3ec8c0d6b.png)



<h1> Performing pre-checks on dataset for implementing algorithms.</h1>

<b> Extract the feature column and target column. </b>
1. From the normalized_data_set, class column is removed and is labelled as X.
2. We considered class column as the target from normalized_data_set and labelled as y.

<b> Split the data for X_train,X_test,y_train,y_test with test size and random state Using Random Undersampling data </b>
1. Test size is taken as 0.3 and random state = 42

<b> Split the data for X_train,X_test,y_train,y_test with test size and random state Using NearMiss Undersampling data </b>
1. Test size is taken as 0.3 and random state = 42 
    
<h1> Start with implementing algorithms. </h1>

<b> KNN classifier </b>
1. k is number of neighbors you want to classify, so here k = 3.
2. Fit and predict the model, this gives y_predict.
3. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<b> Decision Tree Classifier </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<b> Random Forest classifier </b>
1. Here we will use the random state that's already used while splitting the dataset.
2. Fit and predict the model, this gives y_predict.
3. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<b> Logistic Regression </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<b> Artificial Neural Network </b>
1. We took 1 Hidden Layer with 200 neurons
2. Fit and predict the model, this gives y_predict.
3. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<b> Naive Bayes </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<b> Support Vector Machine </b>
1. Fit and predict the model, this gives y_predict.
2. Find the accuracy, precision, recall and f1-score for y_predict with respect to y_test for both the Random and NearMiss Undersampling Technique.

<h1> Implementing ROC and AUC with both the sampling Dataset. </h1>
<b> Finding TPR and FPR </b>

1. We calculated y_predict_probab for all the 7-algorithms. 
2. We found TPR(True Positive Rate), FPR(False Positive Rate) and Threshold for all the 7-algorithms using ROC from sklearn.

<b> Find the AUC and plotting ROC curve. </b>
1. We calculated AUC for all the 7-algorithms using metric. AUC from the FPR and TPR as caluclated in step-2.
2. Then plot the ROC curve with their respective AUC in matlib plot.

<h1> Images of ROC curve using Random Undersampling dataset. </h1>

<b></b>

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/ROCrandom.png)

<b></b>

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/ROCrandomzoomed.png)

<b></b>

<h1> Images of ROC curve using NearMiss Undersampling dataset. </h1>

<b></b>

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/ROCnearmiss.png)

<b></b>

![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/ROCnearmisszoomed.png)


<h1> Confusion Matrix with Random Undersampling Technique dataset. </h1>
<b> Plotting the Confusion Matrix for all the 7-Algorithm in two subplot </b>

1. 1st subplot containing KNN, DecisionTree, RandomForest, LogisticRegression.
2. 2nd subplot containing ANN_Algorithm, naiveBayes_algorithm, svm_algorithm.

<b></b>
    
![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Confusion%20Matrix%20for%20first%204-algorithms.png)
    
<b></b>    
 
![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Confusion%20Matrix%20for%20last%203-algorithms.png)

<b></b>

<h1> Confusion Matrix with NearMiss Undersampling Technique dataset. </h1>
<b> Plotting the Confusion Matrix for all the 7-Algorithm in two subplot </b>

1. 1st subplot containing KNN, DecisionTree, RandomForest, LogisticRegression.
2. 2nd subplot containing ANN_Algorithm, naiveBayes_algorithm, svm_algorithm.

<b></b>
    
![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Confusion%20Matrix%20for%20first%204-algorithms%20(NearMiss).png)
    
<b></b>    
 
![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/Confusion%20Matrix%20for%20last%203-algorithms%20(NearMiss).png)
 
 
 <h> Observations from the Project using the Random UnderSampling Technique </h>
 Now we have all the scores for the 7-algorithms, lets see which one gives the best among the 7-algorithms.
 

![image](https://user-images.githubusercontent.com/100334984/165025065-8650bf17-dba1-4582-927f-82ef075bee38.png)



![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/randomundersampling.png)

<b></b>

<h> Observations from the Project using the NearMiss UnderSampling Technique </h>
 Now we have all the scores for the 7-algorithms, lets see which one gives the best among the 7-algorithms.
 


![image](https://user-images.githubusercontent.com/100334984/166191830-bfdaee7a-5102-49b3-aa63-1e1b5c20a9eb.png)




![image](https://github.com/NehaDas25/DataScience_CS5661/blob/main/nearmiss.png)


From the above mentioned histograms, we observed that the best result was observed with ANN(Artificial Neural Network), with an accuracy of 
95.27%, precision of 96.57%, recall of 94%, ROC of 97.87% and F1-score of 95.27% Using Random Undersampling.

If we use approach 2 (NearMiss) to balance our data the best result was observed with Random Forest with an accuracy of 99.32%, precision of 99.31%, recall of
99.31%, ROC-AUC of 99.85, and F1-Score of 99.31.

So, with this we conclude that for credit card fraud detection algorithm, the best suitable algorithm is ANN (Artificial Neural Network) if we use Random
Undersampling to balance our data. If we use NearMiss to balance our data, we can conclude that the best suitable algorithm is Random Forest.

