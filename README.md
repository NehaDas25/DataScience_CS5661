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
1. Upon checking, all V - features are scaled, except Amount and Time.
2. In our project, we have used MinMaxScaler to make our work more simpler and easier.
3. There are lots of other scalers, but minmax is our best option, since we are intended to ignore intermediate values,
    rather focus on minimum and maximum values.
4. Before scaling vs After Scaling

![image](https://user-images.githubusercontent.com/100334984/159194480-235be599-8efd-4fbf-8130-d5b26af35b64.png)

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
    Test size and random state are taken as user inputs.
    
<h1> Start with implementing algorithms. </h1>

<b> 1. KNN classifier </b>
a. k is taken as user-input for number of neighbors you want to classify.
b. Fit and predict the model.
c. Find the accuracy with respect to y_test.

<b> 2. Decision Tree Classifier </b>
a. Fit and predict the model.
b. Find the accuracy with respect to y_test.

<b> 3. Random Forest classifier </b>
a. Here we will use the random state that's already used while splitting the dataset.
b. User input to enter the number of estimators for Random Forest Classification.
c. Fit and predict the model.
d. Find the accuracy with respect to y_test.

<b> 4. Logistic Regression </b>
a. Fit and predict the model.
b. Find the accuracy with respect to y_test.

<h1> ROC and AUC. </h1>
1. We calculated y_predict_probab for all the 4-algorithms.
2. We found TPR(True Positive Rate), FPR(False Positive Rate) and Threshold for all the 4-algorithms using ROC from sklearn.
3. We calculated AUC for all the 4-algorithms using metric.AUC from the FPR and TPR as caluclated in step-2.
4. Then plot the ROC curve with their respective AUC in matlib plot.

![image]()
