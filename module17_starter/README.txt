Summary findings 

Question Prompt - Our goal was to compare different ML Classification algorithms on the Bank Marketing data for selling Fixed deposit schemes.
Dataset - The data represents 17 marketing campaigns which occurred between May 2008 and November 2010, corresponding to a total of 79354 contacts.

Data Observations
1. The dataset is quite clean as there are no null values in the data set.
2. The numerical and categorical columns are equal in number

Business Objective - 
Predict if the user will subscribe (i.e. buy) a term deposit application by using targeted marketing campaigns. Our task is to find the best possible model which can explain success of subscription with least amount of contacts.

Results
1. Baseline Dummy classifier accuracy score : 0.8865015780529255
2. Simple Logistic Regression accuracy score : 0.911143481427531
3. Model comparisions with LR, KNN, SVC, DT with default parameters
                    Model  Train Time  Train Accuracy  Test Accuracy
0      logisticregression    0.260753        0.911836       0.911143
1                     knn    0.060046        0.928589       0.903010
2                     svc    7.454625        0.921700       0.911143
3  decisiontreeclassifier    0.127044        0.917420       0.915028

4. Model comparision with LR, KNN, SVC, DT with hyper parameters tuning
                    Model  Train Time  Train Accuracy  Test Accuracy
0      logisticregression    1.005735        0.911836       0.911143
1                     knn    0.696004        0.924219       0.904467
2                     svc   19.598402        0.921700       0.911143
3  decisiontreeclassifier    0.255484        0.917420       0.915028

Classifier observations
1. SVC took the longest time to train and Decision Tree classifier took the least time to train
2. Accuracy wise all the models were comparable to each other
3. Given the results we should chose the Decision Tree classifier

Link to Jupyter notebook 
https://github.com/kiks2580/AI_ML_Coursework/blob/main/module17_starter/prompt_III.ipynb