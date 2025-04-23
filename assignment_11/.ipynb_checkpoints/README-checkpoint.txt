Summary findings 

Question Prompt - Our goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.
Dataset - Vehicles dataset containing information on 426K car sales data.

Data Observations
1. We have a lot of categorical columns v/s numerical columns
2. Size, cylinders, condition and VIN columns are most empty. And need to be further inspected
3. VIN numbers are unique for cars and if there are null or duplicated VIN values we should probably fix
4. Size column can be dropped given the large missing data set.
5. Price distribution count plot has a very large skew towards the left and large spread and needs further exploration

Numerical Data Inference
1. Year feature shows a positive correlation with Price of the vehicle
2. Odometer feature shows a negative correalation with the Price of the vehicle

Categorical Data Inferences
1. From the Visual plots we can infer the following
    a. Gas vehicles are the most popular
    b. Ford, Chevy, Toyota, Honda, Nissan are the top 5 manufacturers for vehicles sold
    c. Clean title is the most preferred in a vehicles sale
    d. SUV and Sedan are the 2 most popular type of vehicles sold
    e. White, Black, Silver, Grey , Blue are the top 5 color of the vehicles sold 
2. We donot observe a clear correlation between the Categorical features and the price of the vehicles, we will have to use OHE to figure out if any of these columns are interesting



Link to Jupyter notebook 
