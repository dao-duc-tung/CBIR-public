# Content-based Image Retrieval System

This is a private project. Some results are shown for demonstration purpose only.

# Overview

This CBIR system is build by using the Bag of Visual Words model. Bag of visual words (BOVW) model is a simple way to represent an image. Refer to [this link](https://en.wikipedia.org/wiki/Bag-of-words_model_in_computer_vision) for more detail.

The BOVW model requires a vocabulary which includes the codewords. The codewords are the feature vectors generated from every images in the dataset.

To build the vocabulary, I perform a clustering process on every feature vectors. The codewords now are the cluster centers. Refer to [this link](https://en.wikipedia.org/wiki/Cluster_analysis) for more detail about the clustering methods.

For an arbitrary image, each feature vector of that image is mapped to a certain codeword. The image now is represented by the histogram of codewords.

Given a query image, I will represent it by forming the histogram of codewords. This histogram will be compared with every histogram representation of every images in the dataset by using a distance function. The result of searching process is the scored ouput of this distance function. Refer to [this link](https://en.wikipedia.org/wiki/Metric_(mathematics)) for more detail about the distance function.

# Optimization

To improve the search speed, I build a dictionary with key is the codeword, and value is the list of images which contain that codeword in the dataset. After forming the histogram of codeword for the query image, I get the sorted list of images that share a large number of codeword with the query image. We will search on this list instead of the whole dataset. Refer to [this link](https://en.wikipedia.org/wiki/Inverted_index) for more detail.

To improve the accuracy, I use a technique that can reflect how important a codeword is to the dataset. Refer to [this link](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) for more detail.

# Output Examples

<img src="https://github.com/dao-duc-tung/cbir-public/raw/master/media/1.png" alt="drawing"/>

<img src="https://github.com/dao-duc-tung/cbir-public/raw/master/media/2.png" alt="drawing"/>
