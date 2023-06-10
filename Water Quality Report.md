


# Water Quality Project
## Team members:
- Deema Alkhudairi
- Hisham Altayieb 
- Fai Alamri

Water is an essential resource for all beings yet, it is polluted in many areas around the world. Pollution turned water into a toxic liquid that could cause diseases over time. We used "Water quality" dataset by "MSSMARTYPANTS" from [kaggle website](https://www.kaggle.com/datasets/mssmartypants/water-quality) to see the components that cause water
to be toxic and analyze their relation and run analysis on these components to draw awareness to the importance of water quality.
The dataset contains 7999 entries and 21 features where 20 of them are components that affect the water's cleanliness, and the other feature is the result of the water's safety. Moreover, all the features are numerical except for "ammonia" and "is_safe" features.

![1](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/d6556a4b-6669-4cad-9505-f8847aca86df)

When we checked "ammonia" and "is_safe" features, we discovered that both of them have a value named "#NUM!". We found that the best approach to deal with the unwanted value is to delete it since removing it does not affect variance nor does it change the structure and skewness of our data.

![2](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/e2e70784-32c8-4695-841f-390131c06997)

After cleaning the data, we plotted the correlation map which we drew some insights such as:

 - How impactful aluminium is on our data?
 - How impactful cadmium is on our data?
 - How impactful chromium is on our data?
 - Do bacteria have a negative effect on the water's safety?
 - Does mercury have a negative effect on the water's safety?
 - What are the components that can affect water cleanliness?

### How impactful aluminium is on our data?
To know the effect aluminium on our data, we plotted the results in a histogram plot.

![3](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/c725584c-2dc2-47cd-985f-d3a5bd4b5180)

We conclude that aluminium has a strong negative impact on the water's safety.

### How impactful cadmium is on our data?
Same as above, we plotted the results with a hisogram plot.

![4](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/56789a6f-a1f2-4bf4-aff1-df98676fb1a6)

We drew the same conclusion as aluminium.

### How impactful chromium is on our data?
Similar to aluminium and cadmium, we plot the results with a histogram plot.

![5](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/8cb4f4b0-e003-4a73-bbd8-de24daea3ced)

As expected, we get results almost identical to both aluminium and cadmium.

### Do bacteria have a negative effect on the water's safety?
Bacteria can be beneficial to the human body, so we want to check whether the bacteria in water is harmless or not by plotting a pie chart to see the percentage of bacteria in both safe and not safe water.

![newplot (24)](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/e3e40412-a6eb-4c59-914f-b9d7f1ac833c)

We conclude that bacteria in water is harmful.

### Does mercury have a negative effect on the water's safety?

Mercury is known to be a toxic substance. We want to check how much can mercury affect the water negatively by plotting a bar plot.

![newplot (25)](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/32124f09-c77b-40af-9f4a-697ff7f0a7e5)

Mercury can heavily intoxicate water.

### What are the components that can affect water cleanliness?

To see the effect of every component on water, we plotted the percentage of every element as a pie chat.

![newplot (26)](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/9b49808a-9b5b-4e36-b47b-a8db1881324c)

The top three components mixed with water are:

    1. Salts
    2. Gas
    3. Metal
    
After cleaning data and drawing insights, we discovered that the ratio between the categories of our target feature ('Safe', 'Not safe') is too big which will cause bias in our classification model.

![9](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/d5fdf32e-5013-4a28-8426-7bd3612da8aa)

As you can see, the categories are extremely unbalanced which can be solved by oversampling the data.
After oversampling data, our categories are balanced and ready to enter our machine learning models.

![10](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/781b7c42-cc0a-47a2-b9f1-b2aa99a1387b)

First, we want to visualize the importance of every feature in our data set by using a Random Forest Classifier.

![11](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/b8a162cb-2f83-436b-9be1-c99028cdf689)

Aluminium is the most important feature in the dataset creating a big gap between it and the other features. 

## Models and Scores
Below we have a table of every model used and their classification report.

PP stands for **Predicted Positive**.

PN stands for **Predicted Negative**.

|  Model| Precision| Recall| F1-Score| Accuracy| 
| --- | --- | --- | --- |---| 
| Bagging Classifier | PP=97%, PN=93% | PP=99%, PN=74% |PP=98%, PN=82%| 96%
|Decision Tree | PP=97%, PN=80% | PP=98%, PN=76% | PP=97%, PN78%| 95%
|Gaussian Naive Bayes| PP=95%, PN=37%| PP=87%, PN=61%| PP=91%, PN=46%| 83%
| Support Vector Machine| PP=89%, PN=0%| PP=100%, PN=0%|PP=94%, PN=0%| 89%
|Tuned Decision Tree| PP=96%, PN=79%|PP=98%, PN=68%|PP=97%, PN=73%|94%
|Tuned Support Vector Machine| PP=89%, PN=28%|PP=99%, PN=4%| PP=94%, PN=8%| 88%

### Plotting the Decision Tree Model
At first, we initialized a decision tree with a depth of 21. Then we plotted the tree.

![12](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/4afda727-1aa0-4484-978f-3abdfb31c057)

The tree has many nodes, so we tuned our decision tree and limited the tree's maximum depth to 4.

![13](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/12d66c34-7f63-4423-94de-d0332d31e948)

Lastly, we plotted the accuracy of our models in a line chart.

![14](https://github.com/Nier1419/Bootcamp-Project-4-Machine-Learning/assets/85634276/bdf06324-f579-4c0d-aa52-c4964ffbdd10)

The best fitting model for the water quality dataset are the decision tree and the bagging classifier models.

## Interactive Dashboard

[Click here](https://public.tableau.com/app/profile/deema.abdullah/viz/Water_16862566213540/Dashboard2?publish=yes) to see the dashboard
