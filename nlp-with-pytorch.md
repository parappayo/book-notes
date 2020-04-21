# About

* [Natural Language Processing with PyTorch: Build Intelligent Language Applications Using Deep Learning](https://www.oreilly.com/library/view/natural-language-processing/9781491978221/)
* by Brian McMahan, Delip Rao
* published by O'Reilly, 2019

# Thoughts

Good introduction to the general field of NLP.

# Take-Aways

# Concepts

* `_` suffix - indicates PyTorch function that operates in-place
* Agglutinative Language - morphemes (like words or tokens) are strung together without changes in spelling or pronunciation, may be lacking whitespace and thus a challenge for tokenization; distinct from Inflective Language
* Automatic Differentiation - techniques for calculating the derivative of a function
* Backpropagation - iteratively updating parameters, steps are also called epochs, see also Forward Pass and Backward Pass
* Backward Pass - updates parameters from the gradient of loss
* Chunking - aka Shallow Parsing; tagging a span of text (phrase), eg. break a sentence into the noun phrase and verb phrase
* Computational Graph - abstraction of text, used in deep learning
* Computational Linguistics (CL) - computational methods to analyze properties of languages; eg. how are languages formed, learned, understood
* Constituent Parse - hierarchical grammatical parse of a sentence
* Corpus - body of text, plural corpora
* Deep Learning - new ML techniques, mostly started in 2006; neural net layers are added to boost reliability
* Dependency Parse - sentenced parsed into the relationships between the nouns
* Directed Acyclic Graph (DAG)
* Dynamic Computational Graph - imperative style graph defs, inputs can potentially alter graph structure
* Feature Engineering - applying linguistic knowledge to solve NLP problems
* Forward Pass - computes loss from observations and parameters
* Gradient Descent - incremental method to find roots of an equation; finding weights to minimize the loss function is equivalent; computationally expensive, see also SGD
* Information Retrieval (IR)
* Instance - aka Data Point, text along with metadata; the set of instances is the corpus
* Inverse Document Frequency (IDF) - weight used in TF-IDF; `IDF(w) = log(N) * N(w)` where `N` is the total document count and `N(w)` is the count of documents containing word `w`
* Lemma - root form of a word; conjugations of a word are examples of inflected words
* Lemmatization - convert words to lemmas; spaCy has a `lemma_` property on tokens
* Loss - scalar, used to modify parameters (aka weights)
* Loss Function - in supervised learning, function L, takes Targets and and Predictions, output Loss (modifications to Parameters)
* Machine Learning (ML) - optimizes a set of weights to minimize the cumulative loss over samples
* Matrix - tensor of order 2
* Minibatch SGD - sampling a subset of points
* Model - in supervised learning, takes Parameters (w) and Observations (x), outputs predictions (aka estimations)
* Morphology - study of the forms of words
* N-grams - fixed length token sequences, also bigrams, trigrams, etc.
* Named Entity - commonly called a Proper Noun
* Natural Language Processing (NLP) - applying stats and data structs (vectors, tensors, graphs, trees) to analyze text, typically practical apps such as info extraction, speech recognition, translation, sentiment analysis, queries
* Observations - supervised learning inputs, x; eg. data to be categorized
* One-Hot Representation - aka 1w; sentences are converted to vectors by having a 1 for each word present in the sentence and a 0 for each word absent
* Part-of-Speech Tagging - aka POS Tagging; classify each token as noun, verb, adjective, punctuation, etc.
* Phonology - study of language sounds
* Pragmatics - study of the use of language in context
* Pure SGD - sampling a single point at a time (slow)
* Scalar - tensor of order 0
* Semantics - study of meaning of sentences
* Senses - the different meanings of a word
* Standard Normal Distribution - normal distribution with mean of 0 and variance of 1
* Static Computational Graph - graph is defined and compiled before execution
* Stem - common form of a word, similar to lemma
* Stemmatization - convert words to stems; poor substitute for lemmatization; Porter and Snowball are common stemmer algorithms
* Stochastic Gradient Descent (SGD) - approximates gradient descent; tends to converge slowly, consider Adagrad or Adam
* Stopwords - grammatical purpose, eg. articles and prepositions
* Supervised Document Classification Problem - eg. spam filters
* Supervised Learning - ML with labeled training samples; Observations are inputs to a Model with Parameters (aka Weights), Predictions from the Model are sent to a Loss Function to adjust the weights (Backpropagation)
* Syntax - arrangement of words to correctly form sentences
* Targets - aka Ground Truth, y; supervised learning outputs, the available predictions, eg. categories or labels to assign
* Tensor - multidimensional array; PyTorch methods to slice and index are similar to NumPy matrix methods
* Term Frequency (TF) - aka TF(w); similar to 1w but has the total count of each word, ie. the sum of the 1w of each individual word
* Term Frequency Inverse Document Frequency (TF-IDF) - puts less weight on common words and more weight on rare words; `TF(w) * IDF(w)`
* Tokenization - breaks the corpus up into tokens
* Tokens - words, subwords, symbols that make up text, depends on problem domain
* Types - the unique tokens in a corpus; words are either content words or stopwords
* Vector - tensor of order 1
* Vocabulary - aka Lexicon, the set of all types in a corpus

# Techs

* `FloatTensor` - single precision float is the PyTorch tensor constructor default, but conversion to `DoubleTensor` or other types is easy with `Tensor.double()`, equivalent to `self.to(torch.float64)`
* `requires_grad` - PyTorch setting to require gradient bookkeeping on a tensor
* `torch.randn` - normal distribution, without the n it is uniform distribution
* Alexa - aka Echo, NLP app example
* arXiv - online archive of scholarly articles
* BabelNet - multilingual project similar to WordNet
* Caffe - computational graph framework, static graphs
* Chainer - computational graph framework, dynamic graphs
* Conda - Python package manager, alternative to pip
* CUDA - Compute Unified Device Architecture, by nVidia; for GPU accelerated parallel computation; `torch.cuda.is_available()`
* CUDA Device - use the pattern `device = torch.device("cuda" if torch.cuda.is_available() else "cpu")` and pass device to the `Tensor.to()` method; CUDA and non-CUDA tensors are not compatible types, cannot be mixed in operations
* DyNet - computational graph framework, dynamic graphs
* Eager Mode - TensorFlow feature that allows use of computational graphs with compiling them
* Google Translate - NLP app example
* NLTK - Python lib, Natural Language Toolkit
* PyTorch - computational graph framework, uses tape-based automatic differentiation and dynamic computational graphs; Python and C++ APIs are provided
* scikit-learn - Python machine learning lib
* seaborn - Python data visualization lib based on mathplotlib
* Siri - NLP app example
* spaCy - Python NLP lib, powerful tokenizer
* TensorFlow - computational graph framework, static graphs
* Theano - computational graph framework, static graphs
* WordNet - dictionary used by spaCy for Lemmatization; Princeton University project

# Names Dropped

* Seppo Linnainmaa - introduced automatic differentiation in 1970

# Publications

* Artificial Intelligence: A Modern Approach - book by Russel and Novig
* Feature Engineering for Machine Learning - book by Zheng and Casari
* Foundations of Statistical Natural Language Processing - book by Manning and Schütze
* Natural Language Processing with Python - book by Bird, Klein, Loper
