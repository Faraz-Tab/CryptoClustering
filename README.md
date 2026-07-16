# Crypto Clustering

Unsupervised learning project grouping 41 cryptocurrencies by price-change behaviour, comparing K-means clustering on original features versus PCA-reduced features.

## Data

Market data for 41 coins: price change percentages across multiple time horizons (24h through 1y), standardized with `StandardScaler`.

## Approach

1. Scale features and run the **elbow method** (k = 1–10) on the original data → optimal **k = 4**
2. Cluster with K-means and visualize with interactive hvPlot scatter plots
3. Reduce to **3 principal components** with PCA — retaining **89.5% of total variance**
4. Repeat the elbow method and clustering on the PCA data, then compare both results side by side

## Findings

- The optimal k is 4 in both cases — the cluster structure is stable under dimensionality reduction
- Clustering on 3 components instead of 7+ features produces visually tighter, more separable clusters at a fraction of the feature space
- Two coins consistently isolate into their own single-member clusters, marking them as behavioural outliers

**Tools:** Python · pandas · scikit-learn (KMeans, PCA, StandardScaler) · hvPlot
