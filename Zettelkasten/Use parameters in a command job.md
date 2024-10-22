# Use parameters in a command job

## Notes:

- Can increase the flexibility of scripts by using parameters
- To use parameters in a script use a library like argparse to read arguments passed to the script and assign them to variables
```
import argparse
import pandas as pd
from sklearn.linear_model import LogisticRegression

def main(args):
	df = get_data(args.training_data)

def get_data(path):
	df = pd.read_csv(path)

def parse_args():
	parser = argparse.ArgumentParser()

	parser.add_argument("--training_data", dest="training_data", type=str)

	args = parser.parse_args()

	return args

if __name__ == "__main__":
	args = parse_args()

	main(args)
```
---
Links :: [[DP-100]] [[Computer Science]] [[Cloud]]
Reference ::  [[Azure]]
Type :: #definition
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-15 18:02