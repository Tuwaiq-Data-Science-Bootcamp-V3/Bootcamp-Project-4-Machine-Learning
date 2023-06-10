# Diabetes Prediction using Machine Learning

Team members: Sarah Alyami, Abdulmalik Alsharekh and Hanadi Almoutairy.

<img width="1000" height="500" src="https://github.com/isazHfc/Bootcamp-Project-4-Machine-Learning/blob/main/Figures/Diabetes.png">

## Problem Statement

The problem at hand is to develop a machine learning model that can accurately predict the likelihood of an individual having diabetes based on certain attributes and medical indicators. 

## Objectives

1. Develop a machine learning model that accurately predicts the presence or absence of diabetes based on the provided features.

2. Preprocess the dataset by handling missing values, and encoding categorical variables.

3. Explore and analyze the dataset to gain insights into the relationships between the features and diabetes.

4. Evaluate the performance of the model using appropriate evaluation metrics and cross-validation techniques.

5. Provide a user-friendly interface where users can input their information and receive a prediction regarding their diabetes risk.

## Dataset

### Dataset Source:

We used The Diabetes prediction dataset from kaggle [Click here to access the dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset).

### Dataset Overview:

The dataset provides information about various villas in different neighborhoods, including features such as the number of rooms, bathrooms, property age, property features (e.g., pool, garage, furnished), and other details.

The dataset used for this project contains information related to diabetes prediction. It consists of several columns, each providing specific details about individuals. Here is an overview of the columns in the dataset:

1. Gender: This column represents the gender of the individual, indicating whether they are male or female.

2. Age: This column denotes the age of the individual in years. It provides an important demographic factor for diabetes prediction.

3. Hypertension: This column indicates whether the individual has hypertension or not. It is represented by binary values, where 0 represents the absence of hypertension and 1 represents the presence of hypertension.

4. Heart Disease: This column indicates the presence or absence of heart disease in the individual. Similar to hypertension, it is also represented by binary values, where 0 represents the absence of heart disease and 1 represents its presence.

5. Smoking History: This column captures the smoking history of the individual. It contain categorical values indicating whether the individual is a non-smoker, a past smoker, or a current smoker.

6. BMI (Body Mass Index): This column represents the Body Mass Index of the individual. It is a numerical value that provides insights into the individual's weight status.

7. HbA1c Level: This column indicates the HbA1c level of the individual, which is a measure of the average blood glucose level over the past few months. It is represented by a numerical value.

8. Blood Glucose Level: This column represents the individual's blood glucose level, which is an important indicator for diabetes diagnosis. It is also represented by a numerical value.

9. Diabetes: This column serves as the target variable, indicating whether the individual has diabetes or not. It is represented by binary values, where 0 represents the absence of diabetes and 1 represents its presence.

The dataset provides a diverse set of attributes that can be used to train a machine learning model for diabetes prediction. By analyzing the relationships between these features and the target variable, the model can learn patterns and make accurate predictions regarding the presence or absence of diabetes in individuals.

## EDA and Data cleaning:

### EDA

Exploratory Data Analysis (EDA) is an essential step in understanding and ensuring the quality and consistency of a dataset. The following steps were undertaken to conduct EDA on the dataset:

1. Head: The `head()` function was used to examine the initial rows of the dataset. This provided a quick overview of the data and allowed for a glimpse into the column names and the values contained in them.

2. Shape: The `shape` attribute was utilized to determine the dimensions of the dataset, providing the number of rows and columns. This information helped understand the dataset's size and scope.

3. Info: The `info()` function was employed to obtain a summary of the dataset's structure. It provided insights into the data types of each column and the number of non-null values. This step helped identify missing values or inconsistencies in the dataset.

4. Describe: The `describe()` function was used to generate descriptive statistics for numerical columns. This included count, mean, standard deviation, minimum, quartiles, and maximum values. These statistics provided an understanding of the distribution and variability of the data.

By performing these EDA steps, a comprehensive understanding of the dataset was obtained. It facilitated the identification of any data quality issues, missing values, or outliers. This knowledge served as a foundation for further analysis and modeling, ensuring reliable and accurate results.

Our interactive dashboard offers a concise and visual overview of the dataset, allowing users to explore and analyze key features with ease [Click here to access the dashboard](https://public.tableau.com/views/DiabetesPrediction_16864211715580/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link).

### Data cleaning

1. Missing Values: Through the use of the `isna()` function, it was determined that the dataset does not contain any missing values. This indicates that there are no null or undefined entries in the dataset.

2. Duplicate Rows: A total of 3,854 duplicated rows were identified in the dataset. To address this issue, the duplicate rows were removed while retaining the first occurrence of each row. This was achieved by using the `drop_duplicates()` function, which helped ensure data integrity and prevent duplication-related biases in subsequent analysis.

3. Gender Column: The gender column was found to have three categories: female, male, and other. However, the presence of the "other" category in 18 rows raises concerns about its interpretation and potential impact on the analysis. As a result, it was decided to exclude the rows with the "other" value in the gender column, as handling this category might introduce ambiguity and potentially affect the accuracy of the analysis.

4. In the smoking_history column, there were five distinct values: 'never', 'No Info', 'current', 'former', 'ever', and 'not current'. However, upon analysis, it was observed that some of these values had similar meanings. To ensure consistency and reduce redundancy, a mapping dictionary was utilized to consolidate the values into four categories: 'never', 'No Info', 'current', and 'past'.

The mapping dictionary was used to transform the values as follows:

- 'never' remained unchanged as it represents individuals who have never smoked.

- 'No Info' remained unchanged as it indicates missing or unavailable information regarding smoking history.

- 'current' was used to represent individuals who are currently smoking.

- 'past' was used to represent individuals who have previously smoked, encompassing the categories 'former', 'ever', and 'not current'.

5. The boxplot analysis reveals the presence of outliers in the dataset. In order to address this issue, it is recommended to handle the outliers by applying an appropriate outlier detection and removal technique.

<p align="center">
  <img src="https://github.com/isazHfc/Bootcamp-Project-4-Machine-Learning/blob/main/Figures/outliers.png" alt="Outliers" width="500" height="300">
</p>

- One common approach for handling outliers is to use the Interquartile Range (IQR) method. This involves calculating the IQR for each column, which is the range between the 75th percentile (Q3) and the 25th percentile (Q1). Any data points that fall below Q1 - 1.5 * IQR or above Q3 + 1.5 * IQR are considered outliers and can be dropped from the dataset.

After applying these data cleaning steps, we ended up with a refined dataset consisting of 88177 rows, which will be used for training machine learning models.

## Preprocessing

1. In the preprocessing stage, we utilized the LabelEncoder to encode the categorical columns in the dataset, namely "gender" and "smoking history." This encoding process converted the categorical values into numerical representations, allowing the machine learning models to handle them effectively.

2. After the encoding step, we divided the dataset into two components: the feature set (denoted as "X") and the target set (denoted as "y"). The feature set (X) consisted of all the independent variables or features, while the target set (y) contained the dependent variable or target variable we aimed to predict.

3. Next, we proceeded to split the dataset into training and testing sets. The training set accounted for 70% of the data, while the testing set comprised the remaining 30%. The training set contained 61,723 samples, which were used to train the machine learning models, while the testing set consisted of 26,454 samples and served as an independent set for evaluating the models' performance.

- This division into training and testing sets enabled us to assess how well the models generalize to unseen data and measure their predictive capabilities.

## ML Models

- In this project, we conducted a comprehensive analysis of the Diabetes Prediction dataset, employing various classification algorithms. The algorithms we applied included Decision Tree (DT), Support Vector Machine (SVM), Logistic Regression (LR), Multinomial Naïve Bayes (MNB), and Random Forest.

- Furthermore, we employed Grid Search to optimize the parameters of the Random Forest algorithm, ensuring the best possible configuration for training the model.

- To evaluate the performance of these classification algorithms, we utilized a range of performance metrics. These metrics allowed us to assess the accuracy, precision, recall, and F1-score of each model, providing a comprehensive understanding of their predictive capabilities and overall effectiveness:

<div align="center">

| Algorithm     | Accuracy | Precision | Recall | F1-Score |
|---------------|----------|-----------|--------|----------|
| Decision Tree | 0.95     | 0.95      | 0.95   | 0.95     |
| SVM           | 0.96     | 0.95      | 0.96   | 0.95     |
| Logistic Regression | 0.95     | 0.94      | 0.95   | 0.93     |
| Multinomial Naïve Bayes | 0.79     | 0.91      | 0.79   | 0.84     |
| Random Forest (optimized) | 0.97     | 0.97      | 0.97   | 0.97     |

</div>

- Overall, the Random Forest algorithm (optimized) stands out as the most accurate and reliable model for diabetes prediction, followed closely by SVM and Decision Tree. Logistic Regression also performed well, while Multinomial Naïve Bayes showed relatively lower accuracy but higher precision.

<p align="center">
  <img src="https://github.com/isazHfc/Bootcamp-Project-4-Machine-Learning/blob/main/Figures/performance%20of%20classifiers%201.png" width="500" height="300">
</p>

### Resampling Methods

- Addressing data imbalance is a crucial challenge in data analysis, particularly in classification tasks. Imbalanced datasets, where the number of instances in different classes is significantly skewed, can adversely affect the classification performance. In our project, we encountered an imbalanced dataset with 3224 instances in the "has diabetes" class and 58499 instances in the "medium" class.

- To mitigate the impact of data imbalance, we employed a resampling technique. Resampling involves modifying the dataset to achieve a more balanced representation of the classes. In our case, we opted for an oversampling method. Oversampling involves creating synthetic instances of the minority class to increase its representation in the dataset. This approach allows us to retain valuable information present in the minority class without discarding any data.

- By applying oversampling, we aim to alleviate the negative effects of data imbalance and enhance the classification performance of our models. This technique ensures that the models are exposed to a more balanced distribution of instances, enabling them to learn and generalize better across both classes.

#### Synthetic Minority Over-sampling Technique (SMOTE)

- SMOTE is a popular technique used to address the issue of imbalanced datasets in machine learning. It is an oversampling method that aims to balance the class distribution by generating synthetic samples of the minority class.

- After applying the Synthetic Minority Over-sampling Technique (SMOTE) to address the data imbalance, we aimed to improve the performance of our models. SMOTE generated synthetic samples for the minority class, which in our case was the strong class with only 3224 instances. After applying SMOTE, the minority class was expanded to have the same number of instances as the majority class, totaling 58499 instances.

- We then proceeded to retrain our classification algorithms, including Decision Tree (DT), Support Vector Machine (SVM), Logistic Regression (LR), Multinomial Naïve Bayes (MNB), and Random Forest. By training these algorithms on the balanced dataset, we aimed to leverage the increased representation of the minority class and potentially improve the models' performance.

- After retraining, we evaluated the performance of the algorithms once again using the same performance metrics as before. This allowed us to compare the performance of the models before and after applying SMOTE and determine if there was any improvement in terms of accuracy, precision, recall, and F1-score.

- By incorporating SMOTE and retraining the models, we aimed to address the data imbalance issue and potentially enhance the predictive capabilities of our classifiers, leading to more accurate and reliable results.

- The following table show performance of ML algorithms after applying SMOTE:

<div align="center">

| Algorithm     | Accuracy | Precision | Recall | F1-Score |
|---------------|----------|-----------|--------|----------|
| Decision Tree | 0.95     | 0.95      | 0.95   | 0.95     |
| SVM           | 0.88     | 0.95      | 0.88   | 0.90     |
| Logistic Regression | 0.83     | 0.95      | 0.83   | 0.88     |
| Multinomial Naïve Bayes | 0.61     | 0.93      | 0.61   | 0.72     |
| Random Forest (optimized) | 0.82     | 0.95      | 0.82   | 0.87     |

</div>

- The Decision Tree algorithm stands out as the top performer across all metrics, showcasing its effectiveness in accurately classifying the data. SVM and Logistic Regression also show promising results but exhibit some trade-offs between precision and recall. Multinomial Naïve Bayes struggles to handle the classification task effectively. The optimized Random Forest algorithm achieves a respectable performance but falls slightly behind the Decision Tree algorithm.

<p align="center">
  <img src="https://github.com/isazHfc/Bootcamp-Project-4-Machine-Learning/blob/main/Figures/performance%20of%20classifiers%202.png" width="500" height="300">
</p>

## Friendly-User Interface

- In order to provide a user-friendly interface for predicting diabetes, we developed a Gradio-based application. This application utilizes the Decision Tree (DT) algorithm trained on a balanced dataset to make predictions. The goal is to create a simple and intuitive tool that can be easily used by diabetes professionals, particularly doctors.

- The interface prompts the user to enter the patient's information, including gender, age, hypertension status, heart disease status, smoking history, BMI, HbA1c level, and blood glucose level. The categorical variables, such as gender and smoking history, are encoded using the LabelEncoder function to ensure compatibility with the DT algorithm.

- Once the user submits the information, the DT algorithm predicts whether the patient has diabetes or not. The prediction is displayed as a text output in the interface, indicating whether the patient is predicted to have diabetes or not.

- By offering this user-friendly interface, healthcare professionals can easily input patient data and receive immediate predictions, enabling them to make informed decisions and provide appropriate care. The simplicity and accessibility of the interface contribute to its practicality and usefulness in real-world medical scenarios.

- Example Prediction Result: Patient Not Diagnosed with Diabetes

<img src="https://github.com/isazHfc/Bootcamp-Project-4-Machine-Learning/blob/main/Figures/Interface1.png" alt="Image 1" height="500" width="1000">

- Example Prediction Result: Patient Diagnosed with Diabetes: 

<img src="https://github.com/isazHfc/Bootcamp-Project-4-Machine-Learning/blob/main/Figures/Interface2.png" alt="Image 1" height="500" width="1000">

###### Team members and their roles

<div align="center">

| Tasks     | Sarah Alyami | Abdulmalik Alsharekh | Hanadi Almoutairy |
|---------------|:----------:|:-----------:|:--------:|
| Dashboard of Dataset Overview | &#10004;     | &#10004;      | &#10004;   |
| EDA and Data cleaning           | &#10004;     | &#10004;      | &#10004;  |
| Preprocessing | &#10004;     | &#10004;     | &#10004;   |
| ML Models | &#10004;     | &#10004;      | &#10004;   |
| Friendly-User Interface | &#10004;     | &#10004;      | &#10004;   |

</div>
