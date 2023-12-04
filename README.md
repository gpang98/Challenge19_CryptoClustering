# Challenge19_CryptoClustering

## Overview

This project aim to predict if cryptocurrencies  are affected by 24-hour or 7-day price changes by using unsupervised learning method.

## Objective

The primary goal of this project is to:
- Analyze the predictability of cryptocurrencies by 24-hour or 7-day price changes.  Method employed is unsupervised learning using KMeans.  The results are compared using scaled original dataset using `StandardScaler()` and three principal compenents (`PCA`) with `elbow plots` and cluster plots with `hvplot`.

## Dataset

The dataset `crypto_market_data.csv` was provided for the analysis.

- The original dataset has the following field:
	- coin_id
	- price_change_percentage_24hr
	- price_change_percentage_7d
	- price_change_percentage_14d
	- price_change_percentage_30d
	- price_change_percentage_60d

## Tools and Libraries
- `Python`: Used for data preprocessing, initial analysis, and visualization.
- `Pandas`: Utilized for data manipulation and analysis.
- `hvplot`: Used for data visualization.
- `StandarScaler()` from `sklearn`: Used for Standard scaling.
- `Compute inertia`: To check what is most optimum k-value to use.
- `Kmeans`: Calculate Kmeans using the original scaled dataset.
- `PCA`: Recompute inertia and calculate Kmeans using three principal components (PCA).
- Jupyter Notebook: Employed as the development environment.


## Workflow
- The following are done to complete the exercise:
	- Load and inspect the dataset into pandas dataframe.
	- Scaled the dataset and compute inertia, train the dataset by computing Kmeans and make prediction.
	- Optimise clusters with PCA, compute inertia, train with PCA by computing Kmeans and make prediction.
	- Visualized results of both methods for inertia with `elbow curve` plots and cluster analysis plots for comparison.
	- The following functions are defined to reduce `DRY` (Do Not Repeat Yourself):
        - `compute_inertia_values()`: To compute inertia and generate the elbow dataframe.
        - `plot_elbow_curve()`: To plot the elbow curve using hvplot.
        - `generate_scatter_plot()`: To do scatter plots using hvplot.
    

## Usage

1. **Setup Environment:**
   - Download Jupiter Notebook so that you can run python using Jupyter Notebook as IDE.

2. **Educational Purposes:**
   - Feel free to download the uploaded pages so that you can also explore the dataset and gain insights.

## Main Findings.
- Approximately 89.5% of the variance in the original scaled dataset is explained using three PCAs.
- Visually inspecting both clusters, using fewer features (PCA) was still able to segment the cluster very similarly to using the scaled original data. Most of the clusters are grouped as either 0 or 2 in PCA which corresponds to group 0 and 2 in the scaled original data. Furthermore, the PCA is able to separate the group 1 and 3 better than using the scaled original data where the group 1 seem like is part of group 0 in the scaled original data.


## References

1. Inspired by lectures notes and ChatGPT.
