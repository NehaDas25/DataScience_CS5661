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

<b> Lets see the difference between fraud and genuine transaction.</b>
1. There are 492 fraud transactions and 284315 genuine transactions.
2. Plot looks somehow like this:

<b></b>
![This is an image](https://user-images.githubusercontent.com/100334984/159194089-0bb966b5-4c0c-4fcc-bb75-138c165429b6.png)

<b> Check whether the features are scaled or not:</b>
1. Upon checking, all V - features are scaled, except Amount and Time.
2. In our project, we have used MinMaxScaler to make our work more simpler and easier.
3. There are lots of other scalers, but minmax is our best option, since we are intended to ignore intermediate values,
    rather focus on minimum and maximum values.
4. Before scaling vs After Scaling

![image](https://user-images.githubusercontent.com/100334984/159194480-235be599-8efd-4fbf-8130-d5b26af35b64.png)
