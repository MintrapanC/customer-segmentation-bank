# Customer Segmentation for Banking

Segment bank customers into behavioural groups using K-Means clustering, then translate the resulting profiles into differentiated engagement strategies.

## Problem

Banks serve customers with substantially different spending, income, debt, credit exposure, and demographic characteristics. This project explores whether unsupervised learning can identify meaningful customer segments that support differentiated product and engagement strategies.

## Approach

1. **Data cleaning** - winsorized the clustering variables at the 1st and 99th percentiles to reduce the influence of extreme observations on distance-based clustering.
2. **Exploratory analysis** - examined distributions and relationships across key financial and demographic variables.
3. **Feature scaling** - standardized all clustering variables so that differences in measurement scale did not dominate the distance metric.
4. **Choosing k** - used the elbow method with automatic elbow detection via `kneed`, then compared silhouette scores across candidate cluster counts. The elbow suggested six clusters, while the highest silhouette score was achieved with seven clusters; the seven-cluster specification was therefore used for the final segmentation.
5. **Clustering and validation** - applied K-Means and evaluated the resulting segmentation using silhouette score and pairplot visualisation.
6. **Business translation** - profiled each cluster using average spending, income, wealth, credit limit, debt, and age, then translated the profiles into differentiated engagement strategies.

## Results

The final K-Means specification identifies **seven customer segments**, with a silhouette score of **0.256**, indicating moderate separation between clusters.

The segments differ primarily in spending intensity, income, wealth, credit exposure, debt, and age. For example:

- **High-value affluent customers** combine high spending, income, and wealth with relatively low debt.
- **Young lower-income customers** show lower spending and financial capacity with minimal debt.
- **Young higher-debt customers** combine relatively low income with the highest average debt.
- **High-credit-limit customers** stand out primarily through substantially higher credit limits.

These profiles were translated into differentiated engagement strategies, including premium services, financial support, credit development, and targeted cross-selling.

## Tech Stack

Python · pandas · scikit-learn · K-Means · StandardScaler · silhouette analysis · kneed · matplotlib · seaborn

## Files

- `Clustering_Bank_Customers.ipynb` - full analysis and modelling workflow
- `bank_data.csv` - dataset used for the analysis
