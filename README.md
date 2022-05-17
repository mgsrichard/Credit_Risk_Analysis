# Credit_Risk_Analysis
Using supervised machine learning techniques to predict credit risk

The purpose of this analysis is to evaluate how well 6 different supervised machine learning models predict whether a loan is low or high risk based on a credit card dataset from LendingClub. The models use a variety of approaches: oversampling, undersampling, over and undersampling, and ensemble methods.

# Review of Results of Each Model Considered

## Logisitic Regression with Random Oversampling / Naive Random Oversampling
 - The balanced accurancy score is 64.64%, which is decent but not wonderful
 - The precision score is 99% overall but only 1% for the high risk loans, which means there would be tons of false positives
 - The recall/sensitivity score is 58% overall and for the low risk, and 71% for the high risk. So the model is predicting a high risk loan correctly more than 70% of the time. On the other hand, missing 30% of the high risk loans is still not great.
![naive random](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/naive_random_oversampling.png) <br>

## Logisitic Regression with SMOTE Oversampling
 - The balanced accuracy  score is 65.86%, which is comparable with the score for Naive Random Oversampling, and again, is not the worst, but could be better.
 - The precision score is 100% for the low risk but only 1% for the high risk, so again, there will be many false positives
 - The recall/sensitivity score is 68% overall and for the low risk, and 63% for the high risk. 
![SMOTE](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/SMOTE.png) <br>

## Logistic Regression with Cluster Centroids Undersampling
 - The balanced accuracy score is 54.47%, which is not much better than flipping a coin
 - The precision score is 100% for the low risk but only 1% for the high risk, so again, there will be many false positives
 - The recall/sensitivity score is 40% overall and for the low risk, and 69% for the high risk. 
![cluster centroids](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/cluster_centroids.png) <br>

## Logisitic Regression with SMOTEENN Over and Undersampling
 - The balanced accuracy  score is 62.81%, which compares to that of Naive Random Oversampling and SMOTE Oversampling
 - The precision score is 100% for the low risk but only 1% for the high risk, so again, there will be many false positives
 - The recall/sensitivity score is 60% overall and for the low risk, and 65% for the high risk. 
![SMOTEENN](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/SMOTEENN.png) <br>

## Balanced Random Forest Classifier
 - The balanced accuracy  score is 78.85%, which is a big improvement over the four previous models
 - The precision score is 99% for the low risk but only 3% for the high risk, so again, there will be many false positives
 - The recall/sensitivity score is 87% overall and for the low risk, and 70% for the high risk, both scores a big improvement 
![balanced random forest](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/balanced_random_classifier.png) <br>

 - Below you can see the top section of the list of features by order of importance/influence in the model
![brf features](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/balanced_random_features.png)

## Easy Ensemble Adaboost Classifier
 - The balanced accuracy  score is 93.17%, which is very good
 - The precision score is 99% for the low risk but only 9% for the high risk, so again, there will be many false positives, but an improvement over all other models
 - The recall/sensitivity score is 94% overall and for the low risk, and 92% for the high risk. 
![easy ensemble](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/easy_ensemble.png)


# Summary

The table below summarizes the outcomes of the 6 models, side by side, with conditional formatting that is red when the values are low and shades through yellow and up to green as the numbers increase between 0% and 100%. It allows us to easily see and compare the 6 models. Overall, the two ensemble methods, Balanced Random Forest and Easy Ensemble Adaboost Classifier, outperform the other 4 models. The ensemble approach leads to much improved balanced accuracy scores, precision, and recall. I would recommend using either of these models, especially the Easy Ensemble method. It will produce far fewer false positives and has the highest recall score, which means it misses the fewest high risk loans. There is a little concern about the model being overfitted, but this is balanced by the fact that ensemble models are less prone to overfitting since each weak learner component only uses a small segment of the data.

![excel summary](https://github.com/mgsrichard/Credit_Risk_Analysis/blob/main/Resources/summary.png)

