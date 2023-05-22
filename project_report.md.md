# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME ISAAK MWANGI KAMAU

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
    
I had to assign the values of the predictior to the "count" column of the submission DataFrame / replaced the existing values in the "count" column with the predicted values.

### What was the top ranked model that performed?

WeightedEnsemble_L3

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
    
Through EDA I found that "Season" and "Weather" column were presented as int64 data type while they were supposed to be categorical
Extracted year, month, and day as separate features from "datetime" column adding new features to my dataset
Extract new time-based features "hour_of_day" from the "datetime"
Through EDA I found high correlation between "atemp" and "temp" columns and I decided to drop "atemp" to avoid multicollinearity


### How much better did your model preform after adding additional features and why do you think that is?


There was a substantial increase in model perfomance.

This is because the new feature provide additional information or insights about the target variable, leading to better predictions. Also the new feature may be correlated with the target variable, meaning it has a strong relationship or influence on the target.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
    
    
The model performance decreased

It's possible that the chosen hyperparameter search space is limited and does not contain the optimal values for the given dataset.

I also increase the training time from 10min to 15Min and this might have also lead to model's Overfitting

### If you were given more time with this dataset, where do you think you would spend more time?

Exploratory data analysis and feature creation making notes on how different feature's interact with the model.


### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.



```python
import pandas as pd
pd.DataFrame({
    "model": ["initial", "add_features", "hpo"],
    "hpo1": ["Default", "Default", "'NN': {'num_epochs': 10"],
    "hpo2": ["Default", "Default", "'GBM': {'num_boost_round': 100, 'learning_rate': 0.01}"],
    "hpo3": ["Default", "Default", "'CAT': {'iterations': 50, 'learning_rate': 0.05}"],
    "score": [1.80198, 0.49191, 0.54046]
})

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>model</th>
      <th>hpo1</th>
      <th>hpo2</th>
      <th>hpo3</th>
      <th>score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>initial</td>
      <td>Default</td>
      <td>Default</td>
      <td>Default</td>
      <td>1.80198</td>
    </tr>
    <tr>
      <th>1</th>
      <td>add_features</td>
      <td>Default</td>
      <td>Default</td>
      <td>Default</td>
      <td>0.49191</td>
    </tr>
    <tr>
      <th>2</th>
      <td>hpo</td>
      <td>'NN': {'num_epochs': 10</td>
      <td>'GBM': {'num_boost_round': 100, 'learning_rate...</td>
      <td>'CAT': {'iterations': 50, 'learning_rate': 0.05}</td>
      <td>0.54046</td>
    </tr>
  </tbody>
</table>
</div>



### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![download.png](attachment:download.png)



### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![download%20%281%29.png](attachment:download%20%281%29.png)



## Summary
At the end of this project, I achieved several outcomes and gained valuable knowledge and skills. Here's what I learned and accomplished:

1. __Proficiency with AutoGluon:__
I gained hands-on experience using the AutoGluon library to train and optimize machine learning models for tabular prediction tasks. This enhanced my understanding of AutoGluon's capabilities and its application in real-world scenarios.

2. __Model Training and Optimization:__
I learned how to train multiple iterations of models using AutoGluon, explored different hyperparameters and optimization strategies to improve model performance. This deepened my knowledge of model training techniques and the impact of hyperparameter tuning on model outcomes.

3. __Data Preparation and Analysis:__
Working with the Bike Sharing Demand dataset, I gained insights into data preparation techniques specific to tabular data. This included handling categorical variables, feature engineering, and exploring time-based features. I also analyzed the dataset to identify patterns and relationships that could be leveraged for better predictions.

4. __Kaggle Competition Participation:__
I submitted multiple entries to the Bike Sharing Demand competition on Kaggle, gaining experience in the competition setting. I evaluated my model's performance against other participants and strived for a competitive rank. This experience enhanced my understanding of real-world data challenges and the importance of model performance in a competitive environment.

5. __Report and Public Showcase:__
As part of the project, I completed a report summarizing my findings, insights, and approaches. This report can be shared publicly on Kaggle or my personal page, providing an opportunity to showcase my work and communicate my strategies and achievements to a wider audience.

Overall, this project equipped me with practical skills in using AutoGluon for tabular prediction tasks, enhanced my understanding of data preparation and analysis, and provided valuable experience in participating in Kaggle competitions and sharing my work with the data science community.









```python

```
