# Text Similarity Analysis using Shingling, MinHashing, and LSH

This project demonstrates the application of advanced techniques for analyzing text similarity across a collection of articles from the BBC. Utilizing a dataset of articles written in English, accessible from [BBC Dataset](http://mlg.ucd.ie/datasets/bbc.html), the project aims to explore algorithms for detecting similarities between documents—a fundamental task in natural language processing (NLP) and information retrieval (IR) systems.

## Overview

Implemented through a series of Python functions, this Jupyter Notebook covers the following key processes: `shingling`, `compare_sets`, `min_hashing`, `compare_signatures`, and optionally, `lsh`. Each function contributes to the overall workflow of analyzing and comparing text documents based on their content similarity.

### Shingling

The `shingling` function transforms a given document into a set of k-shingles (substrings of length k). By breaking the document into overlapping 10-character shingles and computing a hash value for each unique shingle, it represents the document as an ordered set of hashed k-shingles. This initial step is crucial for preparing the text data for further similarity analysis.

### Compare Sets

After converting documents into sets of hashed shingles, the `compare_sets` function calculates the Jaccard similarity between any two sets. This measure quantifies the similarity between two sets as the size of their intersection divided by the size of their union, providing an effective way to assess the similarity of documents.

### Min Hashing

To further process the sets of hashed shingles, the `min_hashing` function constructs a MinHash signature for each set. This compact representation is achieved by applying multiple hash functions to the set and recording the minimum value each function produces. The length of the MinHash signature is adjustable, allowing for a trade-off between computational efficiency and accuracy.

### Compare Signatures

The `compare_signatures` function estimates the similarity between two documents based on their MinHash signatures. By calculating the fraction of components in which the two signatures agree, it offers an efficient method to estimate the Jaccard similarity between the original sets of shingles.

### LSH (Locality-Sensitive Hashing)

Optionally, the `lsh` function implements the Locality-Sensitive Hashing technique to efficiently identify pairs of documents with a high likelihood of similarity. By dividing MinHash signatures into bands and hashing them within each band, LSH focuses the comparison on candidate pairs that meet a predefined similarity threshold, thus optimizing the process.

## Dataset

The dataset comprises a diverse collection of BBC articles, providing a substantial basis for testing the text similarity analysis algorithms. The articles cover various topics and are written in English, making them ideal for this analysis. The dataset can be accessed [here](http://mlg.ucd.ie/datasets/bbc.html).
