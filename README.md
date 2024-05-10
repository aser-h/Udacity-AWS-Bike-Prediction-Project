# Udacity AWS Bike Prediction Project Report
 
# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Aser A. Haider

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Negative count values were seen in some predictions, which was not acceptable for submission. To resolve this issue, negative count values were rounded to zero, ensuring all predictions were non-negative before submission.

### What was the top ranked model that performed?
The top-ranked model that performed was the one trained with hyperparameter optimization. It utilized the "WeightedEnsemble_L3" model with a score of 0.47728.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The exploratory data analysis uncovered important findings in the dataset. It showed that factors like temperature and humidity were strongly linked to the demand for bike sharing. It also revealed patterns in bike rental demand based on the hour, day, and month.
To improve the prediction model, new features were created from the datetime column. These included the year, month, day, and hour to account for time-based trends in bike rental demand. Adding these new time features aimed to boost the model's prediction accuracy and better capture nuanced patterns in the data.

### How much better did your model preform after adding additional features and why do you think that is?
The model's performance significantly improved after adding additional features. The initial score was 1.8033, but after incorporating the new features, the score was 0.69561.

This improvement happened because the new features helped the model understand the data better. By including things like the year, month, day, and hour when bikes were rented, the model could see more detailed patterns in when people use bikes. This extra detail helped the model make better predictions, which is why its score improved so much.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The model's performance improved even more after trying different hyperparameters. Initially, with the added features, its score was 0.69561. However, after tuning the hyperparameters, the score was 0.47728. Indicating that the model got even better at making predictions.

The improvement in performance can be attributed to fine-tuning the settings of the model. By experimenting with different hyperparameters, such as the number of boosting rounds and the learning rate, the model was optimized to perform more effectively on the dataset. This resulted in a significant enhancement in predictive accuracy, leading to the better score.

### If you were given more time with this dataset, where do you think you would spend more time?
If I had more time with this dataset, I would work on improving the feature engineering. This means finding new and better ways to get useful information from the existing features, and maybe creating new features to better understand the patterns in the data.
Additionally, I would spend more time adjusting the model's hyperparameters. Tuning these settings can really boost the model's performance and make its predictions more accurate.
I would also do a deeper analysis of the data to uncover any hidden patterns or relationships that weren't obvious at first. This could involve using different visualization techniques or statistical methods.
Overall, focusing on these areas could make the prediction model work even better and reveal more insights from the dataset.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
| model         | hpo1                                           | hpo2                                                     | hpo3                            | score  |
|---------------|------------------------------------------------|----------------------------------------------------------|---------------------------------|--------|
| initial       | None                                           | None                                                     | None                            | 1.80330|
| add_features  | None                                           | None                                                     | None                            | 0.69561|
| hpo           | num_boost_round: 100                           | num_epochs: 10, learning_rate: 0.001, activation: relu | num_boost_round: 150, num_leaves: 50  | 0.47728|


### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](https://raw.githubusercontent.com/aser-h/Udacity-AWS-Bike-Prediction-Project/main/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](https://raw.githubusercontent.com/aser-h/Udacity-AWS-Bike-Prediction-Project/main/model_test_score.png)

## Summary
For this project, AutoGluon was used to predict bike rental demand. A baseline model was first trained and it was observed that it performed  with a score of 1.8033. To improve the model's performance, exploratory data analysis and feature engineering were conducted, which helped identify temporal patterns in bike rental demand. By adding these additional features, the model's performance was significantly enhanced, with score of 0.69561.
Furthermore, hyperparameter tuning techniques were employed to fine-tune the model's settings. This optimization further improved the model's predictive accuracy, resulting in a score of 0.47728. Overall, through iterative refinement of the model and feature engineering, valuable improvements in predictive performance were successfully achieved.
Moving forward, additional refinement and experimentation with different modeling techniques and feature engineering approaches could lead to even better performance. Overall, this project highlighted the effectiveness of AutoGluon in building accurate predictive models for complex datasets like bike sharing demand.