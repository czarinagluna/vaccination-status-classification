# Vaccination Status Classification

![header](data/images/gabriella-clare-marino-HeIz1OoAl-A-unsplash.jpg)

## Overview

Write here.

## Business Problem

Public health agencies may be able to improve their vaccination outreach by understanding people's opinions and behaviors that may be related with whether they receive the vaccine or not. Doing so will guide public health efforts such as education campaigns to focus on the characteristics that are likely to result to vaccination as supported by relevant data. Using national survey responses, I describe vaccination patterns and classify H1N1 vaccination status based on the features in the dataset.

## Data Understanding

The H1N1 Flu Survey from late 2009 and early 2010 collected over 25,000 responses and covered questions about the individual's social, economic, and demographic background, opinions about the virus and the vaccine, and behaviors like protective measures observed. The dependent variable to predict is the individual's vaccination status: `h1n1_vaccine` . The features are described in the [data source](https://www.drivendata.org/competitions/66/flu-shot-learning/page/211/#features_list).

**Imbalanced Dataset**

| class | value_counts |
|---|---|
| 0 | 0.787546 |
| 1 | 0.212454 |

The ratio of class `0` for not vaccinated to class `1` for vaccinated is 80:20 or more concisely 4:1.

![](data/images/fig1.png)

The features with the strongest correlation with H1N1 vaccination status are `doctor_recc_h1n1`, `seasonal_vaccine`, `opinion_h1n1_risk`, and `opinion_h1n1_vacc_effective`.

## Classification Modeling

Classification algorithms are used to predict the binary classes and evaluated using accuracy and precision. Precision is a useful metric in an imbalanced dataset, as accuracy only reflects the underlying class distribution. To address the class imbalance, random oversampling is done by randomly duplicating examples of the minority class `1` in the training set. 

For optimization, a grid search ([code](https://github.com/czarinagluna/vaccination-status-classification/blob/main/GridSearch.ipynb)) is implemented to tune the model hyperparameters.

**Model Performance**

![](data/images/fig5.png)

Precision is important to the business problem because a false positive is more costly than a false negative. Predicting that an individual receives the vaccine but actually does not is worse than predicting that an individual does not receive the vaccine but actually does. To evaluate the success of predictions, precision measures how many are actually vaccinated out of all the people the model predicted to be vaccinated. 

Tuned Models:

![](data/images/fig4.png)

## Results and Recommendations

Confusion Matrix:

![](data/images/fig6.png)

Write here.

**Model Deployment**

Finally, I deploy the Extra Trees model ([demo](https://streamlit.io/)) to demonstrate classification of vaccination status on new survey responses.

***
SOURCE CODE: [Main Notebook](https://github.com/czarinagluna/vaccination-status-classification/blob/main/main.ipynb)

# Contact

Feel free to contact me for any questions and connect with me on [Linkedin](https://www.linkedin.com/in/czarinagluna/).
