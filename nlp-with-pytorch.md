# About

* [Natural Language Processing with PyTorch: Build Intelligent Language Applications Using Deep Learning](https://www.oreilly.com/library/view/natural-language-processing/9781491978221/)
* by Brian McMahan, Delip Rao
* published by O'Reilly, 2019

# Thoughts

# Take-Aways

# Concepts

* `_` suffix - indicates PyTorch function that operates in-place
* Automatic Differentiation - techniques for calculating the derivative of a function
* Backpropagation - iteratively updating parameters, steps are also called epochs, see also Forward Pass and Backward Pass
* Backward Pass - updates parameters from the gradient of loss
* Computational Graph - abstraction of text, used in deep learning
* Deep Learning - new ML techniques, mostly started in 2006; neural net layers are added to boost reliability
* Directed Acyclic Graph (DAG)
* Dynamic Computational Graph - imperative style graph defs, inputs can potentially alter graph structure
* Forward Pass - computes loss from observations and parameters
* Gradient Descent - incremental method to find roots of an equation; finding weights to minimize the loss function is equivalent; computationally expensive, see also SGD
* Information Retrieval (IR)
* Inverse Document Frequency (IDF) - weight used in TF-IDF; `IDF(w) = log(N) * N(w)` where `N` is the total document count and `N(w)` is the count of documents containing word `w`
* Loss - scalar, used to modify parameters (aka weights)
* Loss Function - in supervised learning, function L, takes Targets and and Predictions, output Loss (modifications to Parameters)
* Machine Learning (ML) - optimizes a set of weights to minimize the cumulative loss over samples
* Matrix - tensor of order 2
* Minibatch SGD - sampling a subset of points
* Model - in supervised learning, takes Parameters (w) and Observations (x), outputs predictions (aka estimations)
* Natural Language Processing (NLP) - applying stats and data structs (vectors, tensors, graphs, trees) to analyze text
* Observations - supervised learning inputs, x; eg. data to be categorized
* One-Hot Representation - aka 1w; sentences are converted to vectors by having a 1 for each word present in the sentence and a 0 for each word absent
* Pure SGD - sampling a single point at a time (slow)
* Scalar - tensor of order 0
* Standard Normal Distribution - normal distribution with mean of 0 and variance of 1
* Static Computational Graph - graph is defined and compiled before execution
* Stochastic Gradient Descent (SGD) - approximates gradient descent; tends to converge slowly, consider Adagrad or Adam
* Supervised Learning - ML with labeled training samples; Observations are inputs to a Model with Parameters (aka Weights), Predictions from the Model are sent to a Loss Function to adjust the weights (Backpropagation)
* Targets - aka Ground Truth, y; supervised learning outputs, the available predictions, eg. categories or labels to assign
* Tensor - multidimensional array; PyTorch methods to slice and index are similar to NumPy matrix methods
* Term Frequency (TF) - aka TF(w); similar to 1w but has the total count of each word, ie. the sum of the 1w of each individual word
* Term Frequency Inverse Document Frequency (TF-IDF) - puts less weight on common words and more weight on rare words; `TF(w) * IDF(w)`
* Vector - tensor of order 1

# Techs

* `FloatTensor` - single precision float is the PyTorch tensor constructor default, but conversion to `DoubleTensor` or other types is easy with `Tensor.double()`, equivalent to `self.to(torch.float64)`
* `requires_grad` - PyTorch setting to require gradient bookkeeping on a tensor
* `torch.randn` - normal distribution, without the n it is uniform distribution
* Alexa - aka Echo, NLP app example
* arXiv - online archive of scholarly articles
* Caffe - computational graph framework, static graphs
* Chainer - computational graph framework, dynamic graphs
* Conda - Python package manager, alternative to pip
* CUDA - Compute Unified Device Architecture, by nVidia; for GPU accelerated parallel computation; `torch.cuda.is_available()`
* CUDA Device - use the pattern `device = torch.device("cuda" if torch.cuda.is_available() else "cpu")` and pass device to the `Tensor.to()` method; CUDA and non-CUDA tensors are not compatible types, cannot be mixed in operations
* DyNet - computational graph framework, dynamic graphs
* Eager Mode - TensorFlow feature that allows use of computational graphs with compiling them
* Google Translate - NLP app example
* PyTorch - computational graph framework, uses tape-based automatic differentiation and dynamic computational graphs; Python and C++ APIs are provided
* scikit-learn - Python machine learning lib
* seaborn - Python data visualization lib based on mathplotlib
* Siri - NLP app example
* TensorFlow - computational graph framework, static graphs
* Theano - computational graph framework, static graphs

# Names Dropped

* Seppo Linnainmaa - introduced automatic differentiation in 1970

# Publications

