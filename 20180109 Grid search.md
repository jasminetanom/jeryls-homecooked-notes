# Grid searching 
Brute force method, slow

# Random search
not brute force, search randmomly

RandomizedSearchCV


# Grid search code
knn_parameters = {
    'n_neighbors':[1,3,5,7,9],
    'weights':['uniform','distance']
}

knn_gridsearcher = GridSearchCV(KNeighborsClassifier(), knn_parameters, verbose=1)
knn_gridsearcher.fit(X_train, y_train)

# Grid search attributes

Property 	Use
results.param_grid 	Displays parameters searched over.
results.best_score_ 	Best mean cross-validated score achieved.
*** results.best_estimator_ 	Reference to model with best score. Is usable / callable.
*** results.best_params_ 	The parameters that have been found to perform with the best score.
results.grid_scores_ 	Display score attributes with corresponding parameters