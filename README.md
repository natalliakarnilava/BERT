# Sentiment Analysis
## Project Description
Online store "Wikishop" launches a new service. Users can now edit and add product descriptions, just like in a wiki community. That is, clients suggest their own edits and comment on the changes of others.

We need to create a tool that will look for toxic comments and send them for moderation. The trained model should classify the comments into positive and negative, using a dataset labeled on the toxicity of edits, while the value of the F1 quality metric should be at least 0.75 on the test set.

## Summary
* Data analysis: 
  * found out that the dataset does not contain gaps
  * the target values are unbalanced. 89.8% of values are "0", 10.2% - "1". 
  * The 'text' column contains only unique values, with the average comment spanning 393 characters and the median value being 4720.
* Data Preparation: 
  * reduced comments to lowercase, 
  * got rid of extra characters and stop words, 
  * lemmatized comments, 
  * split the dataset into training and test sets
* Choosing the Best Model:
  * Using GridSearchCV, selected the parameters for the logistic regression and decision tree models. The logistic regression model (hyperparameters C=9 and penalty='l2') turned out to be the best with f1 = 0.765 versus 0.56 for the decision tree model. On the test sample, it gives f1 = 0.771, which satisfies the main customer's requirement for the model.
