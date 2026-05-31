# PCA Analysis of Bitcoin, Ethereum, Gold, and Silver

## Overview

This project applies Principal Component Analysis (PCA) to one year of daily returns for:

* Bitcoin (BTC)
* Ethereum (ETH)
* Gold
* Silver

The objective is to identify the dominant underlying factors driving the behavior of these assets and determine whether the dimensionality of the dataset can be reduced without losing significant information.

---

## Methodology

1. Downloaded one year of historical daily price data from Yahoo Finance.
2. Computed daily percentage returns.
3. Constructed the correlation matrix of asset returns.
4. Performed eigenvalue decomposition of the correlation matrix.
5. Computed principal component loadings and explained variance.
6. Projected the original data onto the principal component basis.

---

## Correlation Structure

The correlation matrix revealed two strongly correlated groups:

| Asset Pair    | Correlation |
| ------------- | ----------- |
| BTC – ETH     | 0.857       |
| Gold – Silver | 0.804       |

Cross-correlations between cryptocurrencies and precious metals were relatively weak, suggesting the presence of distinct market factors.

---

## PCA Results

| Principal Component | Variance Explained |
| ------------------- | ------------------ |
| PC1                 | 51.46%             |
| PC2                 | 40.09%             |
| PC3                 | 4.88%              |
| PC4                 | 3.57%              |

The first two principal components explain:

**91.55% of the total variance**

This indicates that the behavior of four assets can largely be described by only two underlying factors.

---

## Interpretation

### PC1 – Common Market Factor

The first principal component assigned similar weights to all four assets, suggesting a broad factor that captures market-wide movements.

### PC2 – Crypto vs Metals Factor

The second principal component assigned opposite signs to:

* Bitcoin and Ethereum
* Gold and Silver

This factor captures periods in which cryptocurrencies outperform precious metals and vice versa.

---

## PCA Projection

![PCA Scatter Plot](images/pca_scatter.png)

Each point represents a trading day projected onto the first two principal components.

Because PC1 and PC2 explain over 91% of total variance, the original four-dimensional return space can be effectively represented in two dimensions with minimal information loss.

---

## Key Takeaways

* Bitcoin and Ethereum behave as a highly correlated crypto cluster.
* Gold and Silver behave as a highly correlated precious-metals cluster.
* Two principal components explain more than 90% of the variation in the dataset.
* PCA successfully identifies economically meaningful latent factors without any prior knowledge of asset categories.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Yahoo Finance (yfinance)

---

## Future Extensions

* PCA on the top 20 cryptocurrencies
* PCA on NIFTY 50 constituents
* PCA on sector ETFs
* Rolling-window PCA for time-varying factor analysis
* Comparison of covariance-matrix PCA vs correlation-matrix PCA
