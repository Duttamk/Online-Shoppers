# Online-Shoppers
Real Time Prediction Online Shoppers Purchasing Intention

# INTRODUCTION

The dataset in question has been collected from the open repository of University of California Irvine (UCI). It contains 12,330 rows and 18 columns. Each row represents a session of online shopping and the columns represent attributes of each session (like - transaction amount, time spent, etc.).




## ATTRIBUTE INFORMATION

Of all the attributes, 10 are numerical and 8 are categorical. The *Revenue* attribute represents whether a transaction was finalized (TRUE) or not (FALSE).

The attributes: *Administrative*, *Administrative_Duration*, *Informational*, *Informational_Duration*, *Product Related* and *ProductRelated-Duration* represent the number of different types of pages visited by the visitor in that session and total time spent (in seconds) in each of these page categories.

*BounceRates*, *ExitRates* and *PageValues* represent the "Google Analytics" metric. The *SpecialDay* column represents the closeness of the day of transaction to a specific special day (like - Valentines' Day, New Year, etc.). Its values changes for each special day, but ranges from 0 to 1 with "1" being the closest.

*Month*, *Region*, *TrafficType* and *VisitorType* re all categorical features indicating the month of visit, geographical region of the visitor, traffic source of the visitor and whether the person is "returning", "new" or "other" visitor.



# OBJECTIVE AND APPROACH

Classify 30% of the dataset (test data) for the target variable "revenue". Apply Support Vector Machine (SVM) and Random Forest (RF) algorithms for the classifications.

First, introduce *NAs* at random positions in the data through the *prodNA* function from *missForest* package. 

Standardize the numerical columns of the data through Z-score method. Apply Factor Analysis of Mixed Data (FAMD) through the *FAMD* function from *FactoMineR* package. FAMD performs Principal Component Analysis (PCA) of numerical variables and Multiple Correspondence Analysis (MCA) of categorical values, and hence it is favored for mixed datasets. Analyze the FAMD results to select predictors that account for >85% variance in the data.

Using *svm* function from *e1071* package, train the training set to predict for test set. Train *randomForest* function from the package of same name over the training data with unscaled features. Plot both the models and evaluate the SVM and RF models with Cohen's kappa (k) value.

Perform *kmeans* clustering analysis of the dataset using to view groups within the data.



# EXISTING RESEARCH


This dataset has been part of researches, specifically in this [paper](https://doi.org/10.1007/s00521-018-3523-0). Here, they used the LIBSVM implementation with optimized hyperparameter values. Decision tree from C4.5 algorithm and LSTM-RNN were also utilized.


# OUTPUTS

The output along with the code can be viewed on the site : https://duttamk.github.io/Online-Shoppers/index.html
