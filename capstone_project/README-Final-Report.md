### Credit Approval Final Report

#### Executive summary

#### Problem Statement
Based on a user profile (i.e. personal data, and historical loan information) determine if a user is credit worthy.

Credit approval process seems quite opaque. Declines don't necessarily spell out the exact reasons. With this analysis we can interpret what features go into the credit decisioning and inform the users how to improve their chances to gain the necessary credit for their purchase.

#### Data Sources
What data will you use to answer you question?
https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction
1. There were 2 data sets Application data (Rows 438557 and Columns 18) and Credit records data (Rows 1048575 and Columns 3)
2. We merged these 2 data sets on the unique ID field to get a total of unique 777715 rows and Columns 20

#### Data Preprocessing/Preparation: 
Methodology 
1. I first analyzed the Data Analysis with help of statistical and visual graphs to evaluate missing values, columns of interest, etc. The Jupiter notebook has the visualizations.
2. Then I performed EDA (Exploratory Data Analysis) to get the following findings
### Data Observations
1. We have a total of Rows 777715 and Columns 20
    - This dataset contains 9 categorical columns of `object` datatype and 11 columns of `numeric` datatype
    - This dataset contains 1 columns of `object` datatype which shows `Status` of billing details status of creddit card 
2. OCCUPATION_TYPE column has most missing/null values and can be dropped.
3. Loan status has multiple values and we will need to explode them into individual columns for further analysis

4. While there are total 777715 rows, we have 36457 unique IDs or members. There are multiple entries for an ID which is fair because there is an entry for each monthly payment
### Data Observations for Categorical columns
1. Loan status which is our target label is imbalanced  
2. We have more Female members v/s male members. Females are higher in each category of loan status as compared males
3. People who dont own a car seem to make more regular loan payments
4. People who own a property seem to make more regular loan payments
5. People with Secondary education take more credit card loans
6. People who live in owned house or apartment take more loans and also make regular payments 
7. Married people take more loans and also make regular payments
### Data Observations for Numerical columns
1. Family members and number of children columns have a high corelation.
2. Age and is_unemployed also has high corelation
### Feature Engineering and Data split
1. I used StandardScalar() for scaling numerical columns/variables and OneHotEncoder for encoding categorical columns/variables
2. The data was split 80-20 for training and testing data sets.

#### Modeling
1. A simple Logistic regression first as a baseline model
2. Followed by KNN, Decision trees, Random forest and XGBoost as model types to predict if we can underwrite the user for that particular loan amount
3. A tuned the performance by performing a GridSerchCV on KNN and Decision Trees algorithms
4. Random Forest algorithm was tuned by increasing the number of trees

#### Results : Model Evaluations: 
1. Simple Logistic Regression accuracy : 0.5180625293327247

2. Model                     Train Time      Train Accuracy  Test Accuracy  Cross Validation Score   
0  knn                       1.026567        0.752924        0.734369       [0.72589895, 0.72550356]
1  decisiontreeclassifier    1.624816        0.523240        0.525122       [0.52307722, 0.52295828] 

3. GridSearch CV results
                  Model    Train Time        Train Accuracy  Test Accuracy
0                     knn  131.307544        0.760815        0.740856
1  decisiontreeclassifier    4.326800        0.646374        0.638447

4. Random Forest scores
Accuracy Score : 73.91 %
Cross-validated scores: [0.73628802 0.73603086 0.73684845 0.73535368 0.73440539]
Precision Score : 0.74
F1-Score : 0.7391075136778897

5. Tuning the Random Forest Algorithm
Accuracy Score for 1 : 74.76 %
Accuracy Score for 10 : 75.65 %
Accuracy Score for 100 : 75.79 %
Accuracy Score for 500 : 75.81 %

6. XgBoost model scores
Accuracy Score : 60.63 %
Cross-validated scores: [0.60114919 0.60485394 0.6053892  0.60368549 0.60149959]
Precision Score : 0.61
F1-Score : 0.6063275107205082 

7. Overall Random forest algorithm with 100 trees performned the best and had 76% accuracy score and was the fastest. KNN came close with 74% accuracy but took much longer time to train

#### Next steps
1. I believe we can further tune XgBoost model and improve the performance with a GridSearchCV
2. Look into dropping and tuning more variables variables.


#### Outline of project

- https://github.com/kiks2580/AI_ML_Coursework/blob/main/capstone_project/credit_applicaiton.ipynb


##### Contact and Further Information

**Author** 
Laukik Watve (laukikw @ gmail . com)
