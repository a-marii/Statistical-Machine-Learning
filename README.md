  # Who can hear the sirens song?

This project aims to analyse and classify the audibility of the Swedish civil defense siren in order to predict the possibility of a citizen hearing the siren, given it's circumstantial surroundings and personal conditions. For this task, a data file containing circumstantial parameters of various citizens, whether or not they heard the siren among with the location of the siren was provided. The chosen approach was to implement different binary classification methods and compare their performance in order to determine the appropriate choice for the problem at hand. 

A prerequisite in order to determine which method performs the best is to train, test and validate
the models on the same data sets. Therefore the provided data was randomly splitted into a new
test and training data file. The training, validation, and test data were split to ensure the training set contained 70% of the original data, the validation set comprised 20%, and the test set accounted for the remaining 10%.

The chosen input features was "euclidian distance", "age groups", "building", "noise", "in vehicle", "asleep" and "no windows". The feature "age" was converted into "age groups" with gaps of 10 years. Furthermore, coordinates of the nearest horn as well as persons coordinates was combined into a new feature, "euclidian distance". Since direction towards the nearest siren was concluded to not affect whether a person heard the siren or not, this feature was not applied to the models.

The classification methods *logistic regression*, *k-nearest neighbor*, *tree based methods* and *boosting* was implemented separately. By conducting classification using the trained models on a separate test data set, it was possible to compare the results. 

To compare the four classification methods and select the most appropriate model for solving the problem,  we conducted classification on separate test data using classification metrics such as Accuracy, Precision, Recall, and Weighted F1-score. 


| Model     | Accuracy    | Precision    | Recall     |  Weighted F1-Score |
| --- | ----------- | ----------- | ----------- | ----------- |
Logistic Regression |  92.1\% |  92.6\% |  97.2\%  |  94.8\% |
k-Nearest Neighbors |  90.0\% |  90.0\%  |  97.4\%  |  93.6\%  |  
Tree Based Methods |  92.5\% |  93.4\% |  96.7\% |  95.0\% |  
Boosting  |  93.0\% |  92.9\% |  98.1\% |  95.4\% |  

A low recall would mean a higher probability that people would not be informed about approaching dangers in time.  A low precision indicates that the model is making false positive predictions, which is crucial in scenarios where false alarms could lead to unnecessary panic. Therefore, a balance between precision and recall, as reflected in the F1-score, might be crucial for alerting the population to various dangers. We used the weighted F1-score as it provides a more comprehensive evaluation of the model's performance on imbalanced datasets. Given the results obtained,  Random Forest and AdaBoost showed approximately the same results of the weighted F1-score on test data, with a marginal difference of approximately 0.4.  The decision to choose Boosting over Random Forest is supported by the fact that in the context of warning about potential dangers, missing a real event can have serious consequences. Therefore, prioritizing recall becomes crucial and a model *AdaBoost* with higher recall was chosen. 
