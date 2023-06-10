# Machine Learning 

## Team members and their roles:
- Salman almalki:  data clean , EDA , Write model code ,  correlation chart
- Sheikha alobodi :  Write model code , data clean , search for appropriate  model ,data overview chart , correlation chart
- Albandari alshudukhi : search for appropriate model, data overview chart,write markdown


## Introduction
The objective of this project is to perform an exploratory data analysis and machine learning on a dataset about students performance in math course in secondary education to predict the Math Final Grade using Python Libraries such as NumPy, Pandas, Matplotlib , Seaborn , plotly and Scikit-learn.
and find the appropriate regression model 

## Dataset Overview and Source.
- This data approach student achievement in secondary education of two Portuguese schools. The data attributes include student grades, demographic, social and school related features) and it was collected by using school reports and questionnaires. Two datasets are provided regarding the performance in subjects Mathematics (In [Cortez and Silva, 2008].

[Students math grade Data Link](https://archive.ics.uci.edu/dataset/320/student+performance)


## results of ML models
| Regression model  | MAE | MSE | RMSE | R2 score |
| ----------- | ----------- | ----------- | ----------- | ----------- |
|Linear Regression Model| 1.26 | 4.68 | 2.16 | 0.79 |
|Lasso Regression Model| 1.26|4.90| 2.21| 0.78|
|Decision Tree Regression Model | 1.22|3.43|1.85|  0.84 |
|Random Forest Regression Model | 1.02|2.76|1.66|  0.88 |


## conclusion and recommendations 
From the above table , it is clear that for the present problem, the Random Forest Regression performs is the best with highest R2 score (Coefficient of Determination) and lowest RMSE. 

### Resource 
- https://dibyendudeb.com/comparing-machine-learning-regression-models-using-python/




