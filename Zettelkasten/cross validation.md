# cross validation

## Definition:

- Technique used to better evaluate [[Machine Learning Models]]
- Instead of just having a [[training data]] [[testing data]] we also have [[validation data]]
- Cross-validation creates synthetic [[validation sets]] by partitioning [[training set]] into multiple smaller subsets
- One common algorithm for cross-validation is [[K-Fold CV]]
	- partitions the training set into k approximately equal sized subsets (called folds)
	- k rounds of the algorithm
		- Each round chooses one of the k subsets as the [[validation sets|validation set]]
		- Other k - 1 subsets are aggregated into that rounds training set
		- Post training that round's evaluation of the model is done on the one subset chosen as the validation fold. Then the evaluation metric is used to evaluate the model
			- Can be classificaiton accuracy for [[Classification|classification models]]'
			- Can be [[Mean Squared Error (MSE)]], [[Mean Absolute Error (MAE)]], or [[R^2]]
- Can be very time consuming
- [[Cross Validation sklearn]]
---
Links ::  [[Computer Science]] [[Data Modeling with scikit-learn]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-09 20:02