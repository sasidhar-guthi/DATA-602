## Introduction:

Many accidents occur in a Year. Road transport is the most common mode of transport that everyone uses to get from one place to other. Due to certain reasons, accidents occur, I am trying to predict what type of damage is caused to the vehicle involved in the collision. I am going to perform this feature engineering with the help of the following features
•	Thing with which the vehicle collided – HARM_EVENT_DESC
•	The movement of the vehicle – MOVEMENT_DESC
•	Body type of the vehicle – BODY_TYPE_DESC
•	Speed limit at the place of collision – SPEED_LIMIT
•	Vehicle used for towing – TOWED_VEHICLE_CONFIG_DESC
•	If it is a Hit and Run situation – HIT_AND_RUN_FLAG_DESC
•	Area at which the collision occurred – AREA_DAMAGED_CODE_MAIN_DESC
•	If the car is in Parking – PARKING_FLAG_DESC
## Objective:

To Predict the Damage type by vehicle Movement, speed limit, body type, area at which the collision occurred, the object with which it collided, if the vehicle is towed, if it is in parking.

## Data Clean-up:

•	The Data set consists of 1,438,808 rows and 49 columns.
•	After eliminating columns having null values and taking the columns only involved in important features, we are left with 1,367,156 rows and 9 columns.

## EDA Outcomes: 

The EDA outcomes are performed on the features taken, below are the insights gained.
### •	Damage Description:
Many of the Vehicles were left in a Disabling condition followed by Superficial and Functional. Many of the accidents resulted in fatal collisions and were left in a Disabling conditions. 
### •	Vehicle Causing Damage:
Most of the collisions that occurred are with other vehicles. It is a little obvious as most of them occur on the road where other vehicles are running or parked along with the vehicles.
### •	Movement of the Vehicle:
Many vehicles involved in the crash are at a constant speed. We can see collisions with other vehicles at a constant speed from the above observation. 
### •	Body type of the Vehicle:
Vehicles involved in collisions are mostly passenger cars.
### •	Speed Limit:
The area at which maximum collisions occurred is at a speed limit of 25MPH. At a speed limit of more than 55, there is a smaller number of collisions. This is good to see as those could have been fatal and avoiding these is good.
### •	Hit and Run:
The ratio is rather 5 to 95 when it comes to Hit and Run reports. Many of them are not Hit and Run reports.
### •	Area where the damage occurred:
Many collisions are at 6’o clock or 12’o clock which shows us that the collisions were either head-on or rear-end collisions.
### •	Parking:
Just like the Hit and Run distribution the parking distribution also has a 5 to 95 ratio, as many of the collisions are not in parking condition.
### •	Type of Damage caused at places with a certain speed limit:
The Collisions which resulted in a Destroyed result have a speed limit of 30 and above and most of them occurred at a 40-speed limit. Most of the functioning car conditions are at 35 as Disabling also mostly has 35 as a speed limit.

## Modelling and Evaluation.

 #•	The Target variable has 8 classes. I have reduced them to 2 classes because of the time constaint, accuracy and recall scores.
 #• After reducing the classes the distribution of the target variable has shown class imbalances. 
 #• I have used scoring = recall_macro and class_weights = balanced to deal with these class imbalances while training the model.
 #• The Null values in the Dataset are handled by Using SimpleImputer.
 #• The Numerical column (speed limit), is not skewed so I have used mean as the strategy.
 #• For the Categorical columns I have used most frequent as the strategy.

## Models

## Logistic Regression:

 #• HyperParameters used for Logistic Regression are 0.1,10,100
 #• After Secondary search hyper parameter c= 400.
 #• Acheived an accuracy of 58% and a recall of 60%.
 #• The Area Under Curve is 65%.

## Decision Tree:

 #• HyperParameters used for Decision Tree are max_depth = 1,7,15, min_samples_split = 0.1,0.3,0.8.
 #• After Secondary search hyper parameters are max_depth = 5, min_samples_split = 0.05.
 #• Acheived an accuracy of 57% and a recall of 58%.
 #• The Area Under Curve is 62%.

## Gradient Boosting:

 #• HyperParameters used for Gradient Boosting are max_depth = 1,3, n_estimators = 10,20,30.
 #• After Secondary search hyper parameters are n_estimators = 300
 #• Acheived an accuracy of 57% and a recall of 58%.
 #• The Area Under Curve is 67%.

## Random Forrest:

 #• HyperParameters used for Random Forrest are max_depth = 5,10,15, n_estimators = 10,50,100, class_weight = balanced, balanced_subsample, max_samples = 1000,2000,5000.
 #• Acheived an accuracy of 57% and a recall of 58%.
 #• The Area Under Curve is 65%.

## Conclusion:

Logistic Regression and Gradient Boosting are the better Models compared to Random Forrest and Decision Tree. I will recommend predicting the Damage Caused to the Vehicle using Logistic Regression or Gradient Boosting.
