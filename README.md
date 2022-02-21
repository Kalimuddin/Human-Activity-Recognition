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


- Position of GravityAccelerationComponants also matters :

![6](https://user-images.githubusercontent.com/54996809/154896561-2c6440b9-9ced-4496-8aa9-685c1486d839.png)

![7](https://user-images.githubusercontent.com/54996809/154896643-475ec301-608c-487b-a0bb-2585ba9f4110.png)


- Data visualization using t-SNE : perplexities = [2,10,50]) :

![8](https://user-images.githubusercontent.com/54996809/154896943-6bd330dd-de1d-4c22-bb8b-12af72be9b90.png)

![9](https://user-images.githubusercontent.com/54996809/154896948-0c32cdff-a540-457f-9d76-52a58bce1751.png)

![10](https://user-images.githubusercontent.com/54996809/154896956-4b972557-8034-430b-805a-a48f93ea29ba.png)

## Classical ML Models :

- Logistic Regression with Grid Search :
    - Accuracy : 0.9626739056667798
    - F1 Score : 0.96

    ![11](https://user-images.githubusercontent.com/54996809/154900115-2f89fac1-f73c-40e7-9914-761820bf2b86.png)



- Linear SVC with GridSearch :
    - SVC = Support Vector Classifier (SVM)
    - from sklearn.svm import LinearSVC
    - Accuracy : 0.9660671869697998
    - F1 Score : 0.97

    ![12](https://user-images.githubusercontent.com/54996809/154900129-7b6d01ee-a3d3-412b-a427-ee78ac6993ce.png)



- Kernel SVM with GridSearch :
    - from sklearn.svm import SVC
    - Accuracy : 0.9626739056667798
    - F1 Score : 0.96

    ![13](https://user-images.githubusercontent.com/54996809/154900164-26c50e87-3db8-479c-bc2c-8325576baad3.png)

- Decision Trees with GridSearchCV :
    - from sklearn.tree import DecisionTreeClassifier
    - Accuracy : 0.8642687478791992
    - F1 Score : 0.86

    ![14](https://user-images.githubusercontent.com/54996809/154900187-53df6804-6862-420d-ac99-848ebe2f6990.png)

- Random Forest Classifier with GridSearch :
    - from sklearn.ensemble import RandomForestClassifier
    - Accuracy : 0.9131319986426875
    - F1 Score : 0.91 

    ![15](https://user-images.githubusercontent.com/54996809/154900206-887949a1-f1b7-4139-b13e-daa7b8e6f3a3.png)

- Gradient Boosted Decision Trees (GBDT) With GridSearch :
    - from sklearn.ensemble import GradientBoostingClassifier
    - Accuracy : 0.9222938581608415
    - F1 Score : 0.92 

![16](https://user-images.githubusercontent.com/54996809/154900247-72126344-76b2-4ef6-b30b-4276d77dad25.png)

- Comparing all models :

![17](https://user-images.githubusercontent.com/54996809/154900262-b62fc8db-281d-4e49-be60-349a33273ac7.png)

## Deep-learning Model : 









