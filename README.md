# What drives the price of a car?
## Overview:
The goal is to identify key drivers for used car prices and to inform our client, a used car dealership, of our findings.

## Data:
The dataset explored comes from kaggle which originally contained information on 3 million used cars. However, the provided dataset contains information on 426K cars to ensure speed of processing. For more details on the dataset, please refer to the following notebook: [Notebook](https://github.com/ahleung2/What_drives_the_price_of_a_car/blob/main/Leung_Aaron%20_What_drives_the_price_of_a_car.ipynb)

## Findings: 
To quickly recap, the goal is to help our client better understand what attributes drive the prices of used cars. In this project, I created three models to identify the key drivers for used car prices. Described below are the summary of the findings for each respective models as well as conclusions that can be derived based on these findings.

### 1. Linear Regression:
Among the three models, the first model (Linear Regression) performed the worst. In particular, the Test MSE was extremely high (4.466281688553043e+18) which led to the conclusion that this was not a suitable model for extracting meaningful information regarding key drivers.

### 2. Ridge Regression and Lasso Regressions:
Since these two model arrived at comparable results, I decided to combine the discussion of these two models together.

Both the ridge regression model and lasso regression model performed much better, arriving at comparable results. In terms of Test MSE, ridge regression performed slightly better than lasso regression (0.23 vs 0.26). Besides computing Train and Test MSE, we obtained feature coefficients as well as explored feature importance.

In terms of feature coefficients for both models, the top three features remain the same (odometer, age, cylinders) while the fourth and fifth features slightly differ. Based on the results, I believe that we can confidently say that odometer, age, and cylinders are key drivers for used car prices. 

As for feautre importance, the rankings obtained align with our rankings from feature coefficients. This further confirms our key takeaways regarding key drivers for used card prices.

## Conclusion: 

Using a collected dataset of used cars, we were able to identify key drivers of car prices using multiple machine learning models. Across the models, there were no disputes for the top three features important for determing car prices. The first important feature in predicting used car prices is odometer. More specifically, as the value of odometer increase, the price of used car decreases. The second important feature is age. Similar to odomoeter, as the age of the car increases, the price of the car decreases. The last important feature is number of cylinders. Unlike odometer and age, cylinders exhibits a positive relationship to car prices, meaning as the number of cylinders increases, the price of the car increases as well. We have also identified other potentially important features to consider across the two models. In particular, we found that condition of the car, the type of fuel used (in particular deisal) and front wheel drive configuration can have an impact as well. Both the condition of the car and deisal fuel exhibit a positive relationship with price while front wheel drive configurations exhibits a negative relationship. Therefore, if you want to mark used cars at higher prices, prioritize cars with lower odometer readings, newer manufactoring year, and higher number of cylinders.

## Future considerations and Next Steps:

Overall, we were able to extract meaningful data regarding key drivers for used car prices. However, during the data preparation steps, a sizeable amount of data was dropped since it proved difficult to impute missing values without the possibility of introducing bias. Two of the columns that were dropped were 'size' and 'model' which could be important when predicting car price. Therefore, it would be good to collect more complete date regarding these two features and see how the coefficients change. Additionally, it would be interesting to build a model incorporating polynomial degrees and see how it performs relative to the other models.  
