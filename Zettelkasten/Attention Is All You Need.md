# Attention Is All You Need

## [[Transformer]]

- New simple network architecture proposed via this paper
- Dispenses with [[recurrent neural network]] and [[convolutional neural network]] aspects
- More parallelizable and require less time to train
- Relies on an attention mechanism to draw dependencies between input and output
	- Each word in a sentence looks at all the other words and figures out how much attention to pay to each other word
- Transformer relies entirely on [[self-attention]] to compute representations of input and output
- [[Encoder-Decoder Structure]]
## Encoder:

- Encoder is composed of a stack of N = 6 identical layers
- Each layer has two sub-layers
	- [[Multi-head self attention mechanism]]
	- [[fully connected feed-forward network]]
- Employs a [[residual connection]] around each of the two sublayers
- Followed by [[layer normalization]]
	- Output of each sublayer is LayerNorm(x + Sublayer(x)) where Sublayer(x) is the function implemented by the sub-layer itself
	- All sublayers produce outputs of dimension 512

## Decoder:

- N = 6 identical layers 
- Decoder has a 3rd sublayer as well
	- Performs multi-head attention over the output of the encoder stack
- Also uses residual connections around each of the sublayers followed by layer normalization
## Definitions

- [[Attention Function]]






Author:: [[Ashish Vaswani]] 
Type:: #source #paper
Org:: [[Google Brain]] [[Google Research]] [[University of Toronto]]
Link:: [[Computer Science]] [[Artificial Intelligence]]
Topics:: [[Machine Learning]] 
Date:: 2024-09-07 10:21
