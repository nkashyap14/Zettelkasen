# recurrent neural network

## Definition:

- Typically factor computation along the symbol positions of the input and output sequences
- They align the positions to steps in computation times and generate a sequence of hidden states, h_t, as a function of previous hidden state h_(t-1), and the input for position t
- Sequential nature stops it from being [[parallelizable]] which when attempting to train on longer sequence lengths acts as a limiter as memory constraints limit batching across examples

----------------------------------------------------------------------------
A recurrent neural network (RNN) is a type of artificial [[neural network]] designed to process sequential data or time series information. Here are the key aspects of [[RNN]]s:

1. Structure: Unlike [[feedforward networks]], RNNs have loops that allow information to persist from one step to the next.
2. Memory: They can maintain an internal state or "memory" of previous inputs, making them suitable for tasks involving sequences or time-dependent data.
3. Input processing: RNNs process inputs sequentially, one element at a time, while considering the current input and the network's previous state.
4. Applications: Commonly used in [[natural language processing]], [[speech recognition]], [[time series prediction]], and other sequence-based tasks.
5. Variants: There are several variants of RNNs, including [[Long Short-Term Memory (LSTM)]] and [[Gated Recurrent Unit (GRU) networks]], which address some limitations of basic RNNs.
6. Training: RNNs are typically trained using [[backpropagation through time (BPTT)]], a modified version of the standard [[backpropagation]] algorithm.
---
Links :: [[Recurrent Models]] [[Machine Learning]] [[Computer Science]]
Paper ::  [[Attention Is All You Need]]
Type :: #paperdefinition
Date :: 2024-09-07 10:25