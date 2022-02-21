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
