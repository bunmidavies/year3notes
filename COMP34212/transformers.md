[[COMP34212]]
[wiki](https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture))

- transformers are deep neural networks that replace [[convolutional neural networks (CNN)|CNNs]] and RNNs (i.e. LSTMs) with ==self-attention==
- transformers were initially developed by google, and based on a 2017 paper titled [Attention is All You Need](https://arxiv.org/abs/1706.03762)
- text can be converted into numerical representations called tokens, and each token can be converted into a vector using a word embedding table
- transformers can be preferable to recurrent networks, since there are no recurrent units, meaning less training time is required in comparison to the average RNN e.g. a LSTM

- encoder-only transformers are typically used in tasks where only an input sequence needs to be processed (i.e. text classification/sentiment analysis)

# visual transformers

- visual transformers present themselves as alternatives to [[convolutional neural networks (CNN)|CNNs]] - they take images as patches without position encoding as inputs, and a multi-head attention mechanism amplifies the key patches
- output labels are then produced using a [[perceptrons|multi-layer perceptron (MLP)]]
- common examples include the visual transformer and DINOv2
# transformers for NLP

- transformers within language can be applied to a number of scenarios:
	- translation
	- time-series prediction
	- document parsing
	- document summarisation
	- document generation
	- biological sequence analysis
- LLMs typically make use of transformers in all these ways