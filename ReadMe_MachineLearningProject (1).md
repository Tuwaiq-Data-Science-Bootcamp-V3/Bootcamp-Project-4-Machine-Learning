########
Team members: 
Faris Alotaibi
Omar Alkenani
Najlaa Alsowayed 


### Introduction:
Imagine you're looking to rent a chalet or apartment in Riyadh for a purpose, you've been searching for days, scrolling through endless listings online, but you're still not sure what you're looking for, but at all you're focusing on booking counts of specific chalet or department to compare and select good choice for you and your family. 
We've taken on the task of analyzing the Rented Chalet or department, which contains information about various villas located in Riyadh. We want to help you make an informed decision about your purchase by providing insights into the real estate market in Riyadh.
We started by exploring the dataset and identifying the different features that could be useful to potential The tenant and the landlord.


### Problem Statement: 
There are several challenges associated with this project. The first is predicting booking counts, which depends on many factors, such as our datadet is almost complicated to let ML model to train on it on the first time.
Additionally, there may be variability in chalet types and prices, making it difficult to find general patterns from the dataset. There may also be outliers in the data that could skew the results. Finally, we need to evaluate the accuracy and robustness of the predictive model to ensure its effectiveness.

However, if successful, a predictive model for booking count would provide valuable insights to businesses operating in the rental market. By understanding the factors that influence booking counts, businesses can optimize pricing strategies, staffing, and chalet offerings.

Data after cleansing and preprocessing, and before entering to ML model we seperate our data into 4 DataFrame and each dataframe is contains specific Chalet Title type to get more accurate result.  
Then, 4 models built based on these different Dataframe. Polynomial Regression model was chosen because our data doesn't has good correlation at all and this is clear point when you take a look on the Correlation HeatMap. 


### Objectives: 
The goal of this project is to build a predictive model for estimating the booking count of various types of chalets using historical data. The dataset used for this project contains information about the chalet type, final price, and the number of bookings made for each chalet, etc.
 The aim is to develop an accurate model that can predict the number of bookings for a given rating of chalet and final price based on historical patterns and trends.

Dataset Overview and Source:
Dataset taking from popular saudi application named with (GatherIn) which is platform licensed by the Ministry of Tourism for peer to peer renting in Saudi Arabia. We display through the platform many private vacation homes (such as villas and private apartments, farms, chalets, resorts, camps, and other vacation homes).
Our columns After cleansing and preprocessing:
- Date: contain date of renting chalet
-Unit_id: contain unique ID for unit written in integer  
- Chalet_id: for every chalet has unique ID written in integer   
- Code: it represent for each neighborhood has an unique code written in integer  
-Final Price: price for rented chalet written in float
-Booking Count: how many booking counts for specific chalet in integer type.
-Rating: Rating for each chalet written in float. 
-Chalet_title: Chalet categories and svaing 6 categoriers written in string
-Neighborhood: Neighborhood for this specific chalet written in string
-City: Riyadh for all row written in string 

| Polynomial Regression Model      | ML Result| '
| :---        |    :----:   |          ---: |
| First Data Frame      |  Training R2: 0.06 Testing R2: 0046 MAE:0032 MSE:0.0023  RMSE:0.048 |   |
| Second Data Frame  | Training R2: 0.0325 Testing R2: 0.0038 MAE: 0.0601 MSE: 0.0073 RMSE:  0.085  | |
| Tird Data Frame | Training R2: 0.738 Testing R2: 0.99 MAE: 0.00037 MSE: 3.9e-07 RMSE:  0.000599  |  |
| Fourth Data Frame  | Training R2: 0.091 Testing R2: 0.036 MAE: 0.046 MSE: 0.007 RMSE:  0.083  |  |
Linear Regression Model | R2: 0.0032 |
