# Bacteria Prediction
Predicting bacteria species based on repeated lossy measurements of DNA snippets.

Solution to the Kaggle's Tabular Playground Series (Feb 2022) competition.

https://www.kaggle.com/c/tabular-playground-series-feb-2022/overview

## The Task

The task is to classify 10 different bacteria species using data from a genomic analysis technique that has some data compression and data loss. In this technique, 10-mer snippets of DNA are sampled and analyzed to give the histogram of base count (Raman spectroscopy). In other words, the DNA segment **ATATGGCCTT** becomes **A2T4G2C2**. We want to accurately predict bacteria species starting from this lossy information.

## The Data

We will predict bacteria species based on repeated lossy measurements of DNA snippets.
Each row of data contains a spectrum of histograms generated by repeated measurements of a sample, each row containing the output of all 286 histogram possibilities (e.g., **A0T0G0C10** to **A10T0G0C0**) which then has a bias spectrum (of totally random ATGC) subtracted from the results.
The data (both train and test) also contains simulated measurement errors (of varying rates) for many of the samples, which makes the problem more challenging.
The dataset is provided by Kaggle, in which the training set contains 200000 row, each one with 286 dimensions.

## Solution Approach

After an initial analysis of the dataset it's evident that we are working with very high dimensional data, which can make the learning process more difficult.
We will start by trying to mitigate this problem by using a dimensionality reduction technique like PCA (Principal Component Analysis).
Then we will use the transformed data to train different machine learning models in order to find the most appropriate architecture to solve the task.

