  # Statistical-Machine-Learning

  This project aims to analyse and classify the audibility of the Swedish civil defense siren in order to predict the possibility of a citizen hearing the siren, given it's circumstantial surroundings and personal conditions. For this task, a data file containing circumstantial parameters of various citizens, whether or not they heard the siren among with the location of the siren was provided. The chosen approach was to implement different binary classification methods and compare their performance in order to determine the appropriate choice for the problem at hand. Firstly, a thorough analysis of certain parameters of the provided data set was completed. The analysis concluded that the correlation between angle towards nearest horn and hearing the siren was low, and therefore, *near angle* -feature was excluded from the training data set. Also the *age*-feature was modified during preprocessing of the data. Secondly, the classification methods *logistic regression*, *k-nearest neighbor*, *tree based methods* and *boosting* was implemented separately. By conducting classification using the trained models on a separate test data set, it was possible to compare the results. This revealed that Random forest and AdaBoost had approximately equal performance. However, for this particular problem Boosting was concluded to be the suitable choice of method, since it has the highest weighted F1-score and Recall. 
