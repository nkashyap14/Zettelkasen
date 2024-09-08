# Design a machine learning operations solution

## General Details

- MLOps helps scaling the model from a POC to production which is ready for large scale deployment and can be retrained when necessary
- Steps to prepare and operationalize a model:
	- Convert model training to a robust and reproducible pipeline
	- Test the code and model in dev
	- Deploy model in prod
	- Automate the end to end process
- Good policy is when you prepare a model for prod you should design for retraining
- Approaches for retraining:
	- Based on schedule
		- Can retrain every week or month when you know you always need the latest model
	- Based on emtrics
		- Monitor the model's performance and [[Data drift]] and retrain when necessary
- Ideally train models with scripts rather than notebooks as they are more suited for automation
	- Can be parameterized
	- Host scripts in a central repository to achieve [[source control]]
- Can configure [[Azure Machine Learning]] jobs to automatically run scripts via pipelines or trigger based on an event
	- Can trigger the job from another tool
	- IE [[Azure Devops]] or [[Github Actions]]
## Subsections

## Terms defined

- [[Machine Learning Operations (MLOps)]]
- [[Data drift]]

Type :: #topic
Links :: [[DP-100]] [[Azure]]
Book :: 
Date ::  2024-09-08 07:55