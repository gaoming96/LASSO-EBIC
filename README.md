# LASSO-EBIC
LASSO (least absolute shrinkage and selection operator) with EBIC (extended bayesian information criterion) to achieve enhanced variable selection in Multi-logistics model.

Here, we extend LASSO into Group LASSO and Sparse Group LASSO while extend BIC into EBIC simultaneously to achieve fairly sparse model.
See `Midterm_report2.html` for quick `R::glmnet` and `R::grpreg` realization for all the models.

## Abstract

In machine learning and statistics, classification is one of the most common supervised learning methods considered. In general, we have many samples of data whose category memberships are known and want to identify which category a new observation belongs to. Each sample is a multi-dimensional entry and it is said to have several predictors or features.

Here, we analyze the Singapore Eye Dataset which contains around 2700 samples of 300 predictors each. These predictors include blood data, eye data, body index and a binary categorical variable (heart disease). We expect to get a simple and practical model to predict whether a person suffers heart disease with the help of some of the above predictors.

Due to the efficiency in clinical medicine, we use Logisitic Model as the classifier. In order to achieve feature selection, some Regularization Methods have been combined to the original model: LASSO (least absolute shrinkage and selection operator), Group LASSO (which selects important factors rather than variables in lasso) and Sparse Group LASSO (SGL, which is sparse at both the group and individual feature levels).

Next, we tune the hyperparameter in these penalized models. Some well-known tuning criteria are implemented: Cross Validation (CV) with deviance as the loss function, CV with misclassification rate as the loss function, Bayesian Information Criterion (BIC) and Extended Bayesian Information Criterion (EBIC, which is more parsimonious).

Finally, we try to measure goodness of fit of the models with some indexes: Correct Classification Rate (CCR), Area Under receiver operating characteristic Curve (AUC) and Polytomous Discrimination Index (PDI).
After applying all these procedures to the dataset, we assert that SGL with EBIC parameter tuning gives the best model containing only 8 predictors.

## Stucture of files

### Theoretical concepts

* `defense_first` (the first defense PPT) contains LASSO group and EBIC group. Specificly, we show the algorithms (Coordinate Descent for LASSO with Linear 
and Block Coordinate Gradient Descent for SGL with Logistic) and the formulas (Cross Validation and EBIC).

* `dissertation_first` (first draft) is more detailed than the final version. Namely, it covers more about MLP (Multi-Layer Perceptron), degree of freedom (especially in complex model 
with the help of Stein's Lemma and give a credible degree of freedom of Group LASSO) and some advanced criterion (PDI and NRI).

* `dissertation_final` (final paper) contains all.

### Numerical results

* `defense_second` (the second defense PPT) contains numerical results of all the above algorithms (eg: how EBIC selects the best hyperparameter in LASSO model).

* `Midterm_report2` is a great and detailed Rmd interactive file to achieve all the LASSO group and EBIC (using `glmnet` and `grpreg`).

* `rchart_get_html` and outputs `CCR_test` (output results for model comparison) give great interactive plots using `rchart`.

* `dissertation_final` (final paper) contains all.
