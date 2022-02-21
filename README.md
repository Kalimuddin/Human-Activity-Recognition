# Human-Activity-Recognition

## Problem Definition and Data Requirements :
- Problem Statement is to predict the human activity such as Walking, Walking Upstairs, Walking Downstairs, Sitting, Standing or Laying.
- After doing EDA and Experimenting so many classical ML models on "already designed features by domain expert" we achieved best Accuracy = 96.61% and F1 Score = 0.97
- And by applying just simple LSTM's on raw time series data without any domain expert we got Accuracy = 90.09%.
- Required Data available at : https://drive.google.com/drive/folders/1S2-8okykGSCHsbmjKVa1jN-zBA0nJzIy?usp=sharing

- In the dataset, Y_labels are represented as numbers from 1 to 6 as their identifiers :-
    - WALKING as __1__
    - WALKING_UPSTAIRS as __2__
    - WALKING_DOWNSTAIRS as __3__
    - SITTING as __4__
    - STANDING as __5__
    - LAYING as __6__

- How data was recorded :- 
    - By using the sensors(Gyroscope and accelerometer) in a smartphone, they have captured '3-axial linear acceleration' (tAcc-XYZ) from accelerometer and '3-axial angular velocity' (tGyro-XYZ) from Gyroscope with several variations.
    - prefix 't' in those metrics denotes time.
    - suffix 'XYZ' represents 3-axial signals in X , Y, and Z directions.

- The magnitude of these 3-dimensional signals were calculated using the Euclidian norm :
    - This magnitudes are represented as features with names like : tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag and tBodyGyroJerkMag.

## Data Cleaning / Preprocessing :
- No of duplicates in train: 0
- No of duplicates in test : 0
- We have 0 NaN/Null values in train
- We have 0 NaN/Null values in test

- Check for data imbalance : We have got almost same number of reading from all the subjects, Our data is well balanced (almost) :

![1](https://user-images.githubusercontent.com/54996809/154895974-0a66de26-b114-44c0-9111-5baa92007983.png)

![2](https://user-images.githubusercontent.com/54996809/154895981-3976c430-f71d-440d-bb24-454e1a33fef9.png)

## EDA :
- Stationary and Moving activities are completely different :

![3](https://user-images.githubusercontent.com/54996809/154896135-0a96872f-b6cf-40e9-9e3a-415926c6879a.png)

- For plotting purposes taking datapoints of each activity to a different dataframe :

![4](https://user-images.githubusercontent.com/54996809/154896292-73a9cacc-79fe-4377-a368-e0db8bef0042.png)

- Magnitude of an acceleration can saperate it well :

![5](https://user-images.githubusercontent.com/54996809/154896428-86ce20e2-c17a-4bd5-ac00-afdaca365661.png)










