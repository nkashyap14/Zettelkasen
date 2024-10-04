# Find the best classification model with Automated Machine Learning

## General Details

- Can automate the testing and evaluation of various configurations for training a machine learning model with Automated Machine Learning or AutoML
	- Allows us to try multiple preprocessing transformations and algorithms with the data to find the best model
- In order for AutoML to understand how to read the data requires the creation of a MLTable data asset that includes the schema of your data
	- stores the data in a folder together with a MLTable file
- AutoML applies scaling and [[Normalization]] to numeric data automatically
	- prevents large scale features from dominating training
- Can choose to have AutoML apply preprocessing transformations like:
	- Missing value imputation to remove nulls
	- [[Categorical Encoding]] to convert [[categorical features]] to numeric indidcators
	- Dropping high cardinality features like record IDs
	- Feature engineering
		- Deriving individual date parts from DateTime Features
- [[Classification]] algorithms offered:
	- [[Logistic Regression]]
	- [[Light Gradient Boosting Machine (GBM)]]
	- [[Decision Tree's]]
	- [[Random Forest]]
	- [[Naive Bayes]]
	- [[Linear Support Vector Machine]]
	- [[XGBoost]]
	- and more
- By default randomly selects from full range of algorithms but you can block algorithms from being selected
- When we've enabled featurization 3 data guardrails are automatically applied and supported for classification models:
	- Class Balancing Detection
	- Missing feature values imputation
	- High cardinality feature detection
- Each guard rail has 3 possible states:
	- Passed: No problems detected and no action required
	- Done: Changes applied to the data. SHould review the changes AutoML has made
	- Alerted: An issue was detected but couldn't be fixed. Review the data to fix the issue
## Subsections

- [[Configure an AutoML Experiment (Code)]]
- [[Submit an AutoML Experiment (CODE)]]
- [[Set the Limits + Specify Primary Metric (AUTOML Code)]]
## Terms defined


Type :: #topic
Links :: [[DP-100]] [[Azure]] [[Cloud]] [[Computer Science]] [[Azure Machine Learning]]
Book :: 
Date ::  2024-10-01 14:10