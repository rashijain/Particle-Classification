# Particle-Classification

Overview: https://www.kdd.org/kdd-cup/view/kdd-cup-2004/Data

The goal of this project is to learn a classification rule that differentiates between two types of particles generated in high energy collider experiments. It is a binary classification problem with 78 attributes. The data set has 50,000 examples. Our task is to build a classification model that optimizes ROC area (maximize).

In this project, we are building Logistic Regression (with and without interaction terms), Random Forest and Gradient Boosting models. 
We find missing values for 8 columns and impute the missing values using mean value for each column. Then we find set of important features using Backward Elimination method as below:
['feat4', 'feat8', 'feat12', 'feat13', 'feat14', 'feat15', 'feat20', 'feat31', 'feat40', 'feat42', 'feat56', 'feat63', 'feat66', 'feat69', 'feat70', 'feat71', 'feat75']
The Logistic Regression models (with and without interaction terms) result in better performance when built upon set of important features. Logistic Regression model without interaction terms results in AUC value of 0.7915 and Logistic Regression model with interaction terms results in AUC value of 0.7912.
We also built a Random Forest classifier to classify the particle types. For this model, we used all the variables to build a prediction model. This resulted in a higher AUC value of 0.8081.
Further, we trained Gradient Boosting classifier with all the variables in the data set. This resulted in the highest AUC value of 0.8266, making Gradient Boosting as the best model among all the developed models. 

The various performance metrics of the developed models can be found in the table below:
| Model |	Confusion Matrix | Accuracy Rate | True Positive Rate	| False Positive Rate	| Precision |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| Logistic regression without Interaction Term | [[3602 1440] [1497 3461]] | 0.7063 |	0.6980 | 0.2856 | 0.7061 |
| Logistic regression with Interaction Term |	[[3607 1435] [1496 3462]]	| 0.7069 |	0.6982 | 0.2846 | 0.7069 |
| Random Forest	| [[3741 1301] [1512 3446]] |	0.7187 | 0.6950 | 0.2580 | 0.7259 |
| Gradient Boosting	| [[3740 1302] [1388 3570]]	| 0.7310 | 0.7200 | 0.2582 | 0.7327 |
