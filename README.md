# Project Description - Prediction of Heart Disease in Patients

Mortalities due to heart diseases are the first cause of death worldwide. Thereby, early diagnosis or prediction of the disease in patients plays an important role in imporving public health and saving lives and families. Analyzing large quantities of data to predecit the disease with machine learning (ML) algortihms have been a challenge and opportunity to reach this goal. In this project, we will try to use multiple data entries from patients to train and test a model that could predict heart diseases, minimizing the false negatives (FNs). Our collective goal is to develop a model that has produces lowest FNs as it would be detrimental for the patients lives.


## Features:
Here we can take a look at the patients' features to better understand the dataset.
* Age: age of the patient [years]
* Sex: sex of the patient [M: Male, F: Female]
* ChestPainType: chest pain type [TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal Pain, ASY: Asymptomatic]
* RestingBP: resting blood pressure [mm Hg]
* Cholesterol: serum cholesterol [mm/dl]
* FastingBS: fasting blood sugar or being diabetes or not. [1: if FastingBS > 120 mg/dl, 0: otherwise]
* RestingECG: resting electrocardiogram results [Normal: Normal, ST: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV), 
* LVH: showing probable or definite left ventricular hypertrophy by Estes' criteria]
* MaxHR: maximum heart rate achieved [Numeric value between 60 and 202]
* ExerciseAngina: exercise-induced angina [Y: Yes, N: No]
* Oldpeak: oldpeak = ST [Numeric value measured in depression]
* ST_Slope: the slope of the peak exercise ST segment [Up: upsloping, Flat: flat, Down: downsloping]
* HeartDisease: output class [1: heart disease, 0: Normal]

![alt text](https://github.com/javadfarshchi/Prediction-of-Heart-Disease-in-Patients/blob/main/corr.png?raw=true)

## Exploratory Data Analysis (EDA)
After performing comprehensive data exploration (found [here](https://github.com/javadfarshchi/Prediction-of-Heart-Disease-in-Patients/blob/main/heart-disease-prediction_LogisticRegression.ipynb)), we have list the most important observations:

1. In terms of total cholestrol levels, healthy and diagnosed patients had similar levels. Thereby, we cannot draw a conclusion solely based on the cholestrol levels.
2. Among the four chest pain types recorded, most of the asymptomatic patients were in fact having heart diseases that makes the disease a silent killer.
3. Investigating age factor among the patients,  it can be established that although heart disease can happen even in early 30s, majority of patients with heart disease are in their mid 50s to mid 60s. It can also be illustrated that the ratio of diagnosed to healthy patients were much higher in men compared to women.
4. Studying patients' resting blood pressure and electrocardiogram (ECG) results, it can be established that healthy patients and patients with heart diseases had almost similar resting blood pressures that indicates resting BP cannot be an indicator of heart disease. Similarly, more than half of patinets with a normal ECG were in fact diagnosed with heart disease. For the case of patients with ST and LVH ECG data, the majority of the patients were finally diagnosed with heart disease. Thereby, resting blood pressure and ECG cannot be solely used for the purpose of diagnosis and other indicators should be used to complement analysis.
5. It was observed that most diabetic patients were diagnosed with heart disease that amplifies the importnace of regular checkups of diabetic patinets for heart diseases.
6. Two of the most important tests to diagnose heart diseases are exerciese tests and maximum heart rates. Most patients with an exercise-induced angina had a heart disease which was also expected. It can also be infered that patients with heart disease could achieve lower maximum heart rate compared to the healthy patients.
7. The ST/heart rate slope (ST/HR slope), has been proposed as a more accurate ECG criterion for diagnosing significant coronary artery disease (CAD). It was established that having a flat ST Slope is a strong indicator of having a heart disease among patients.

## Logistic Regression Modelling and Evaluation of Model
As mentioned, in this model we aim to minimize the rate of false negatives. In the modelling steps also found [here](https://github.com/javadfarshchi/Prediction-of-Heart-Disease-in-Patients/blob/main/heart-disease-prediction_LogisticRegression.ipynb), we have converted the categorical data into dummy variables to be used in hte model. Multiple fold values were investigated fo rthe model to obtain the lowest false negative values possible. Below are the results of the model with different fold values:

The fold is : 0 : 

              precision    recall  f1-score   support

           0       0.82      0.93      0.87        82
           1       0.93      0.83      0.88       102

    accuracy                           0.88       184

The accuracy for Fold 1 : 0.8800813008130083

[[76  6]

 [17 85]]
 
The fold is : 1 : 

              precision    recall  f1-score   support

           0       0.79      0.90      0.84        82
           1       0.91      0.80      0.85       102

    accuracy                           0.85       184


The accuracy for Fold 2 : 0.8531802965088474

[[74  8]

 [20 82]]
 
The fold is : 2 : 

              precision    recall  f1-score   support

           0       0.96      0.65      0.77        82
           1       0.78      0.98      0.87       102

    accuracy                           0.83       184

The accuracy for Fold 3 : 0.8133668101386896

[[ 53  29]

 [  2 100]]
 
The fold is : 3 : 

              precision    recall  f1-score   support

           0       0.88      0.80      0.84        82
           1       0.85      0.91      0.88       101

    accuracy                           0.86       183

The accuracy for Fold 4 : 0.8578845689446993

[[66 16]

 [ 9 92]]
 
The fold is : 4 : 

              precision    recall  f1-score   support

           0       0.69      0.76      0.72        82
           1       0.78      0.72      0.75       101

    accuracy                           0.74       183


The accuracy for Fold 5 : 0.7394349191016663

[[62 20]

 [28 73]]
