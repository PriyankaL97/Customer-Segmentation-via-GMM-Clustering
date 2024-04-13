# Customer Segmentation using GMM Clustering

## Overview
This project analyzes a dataset containing data on various customers' annual spending amounts in diverse product categories to understand the variation in different types of customers that a wholesale distributor interacts with. The goal is to segment customers based on their purchasing behavior, allowing the distributor to structure their delivery service to meet the needs of each customer segment.

## Dataset
The dataset used for this project can be found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Wholesale+customers). For this analysis, the features 'Channel' and 'Region' are excluded, focusing instead on the six product categories recorded for customers.

## Data Exploration
- Visualized feature distributions to understand relationships between features.
- Selected sample data points for tracking through the analysis.

## Data Preprocessing
- Applied logarithmic scaling to handle non-normally distributed data.
- Detected and optionally removed outliers using Tukey's method.

## Feature Transformation
- Used PCA to reduce dimensionality and discover compound combinations of features that best describe customers.
- Explored the explained variance ratio to determine the number of dimensions necessary for the problem.

## Clustering
- Used Gaussian Mixture Model (GMM) clustering for customer segmentation.
- Evaluated clustering using silhouette scores.
- Visualized clusters in reduced PCA space to understand underlying customer segments.

## Utilizing Clustered Data
- Evaluated the effect of a change in delivery service on different customer segments.
- Used customer segments as an engineered feature for labeling new customers.
- Visualized underlying distributions to validate clustering results.

## Results
- Total variance explained by the first and second components: 68.32%.
- Total variance explained by the first four components: 92.44%.
- Segment 0 represents an establishment that can be a factory that uses huge amount of Detergents and/or Paper materials along with Groceries. We can also see the features "Detergents_Paper" and "Grocery" in the heatmap for Segment 0.
- Segment 1 represents an establishment that can be a ice-cream parlor/restraunt that uses Fresh and Frozen materials in large quantities. We can also see the features "Fresh" and "Frozen" in the heatmap for Segment 1.
![image](https://github.com/PriyankaL97/Customer-Segmentation-via-GMM-Clustering/assets/166748907/291fe22b-3f1f-4707-bd0a-254eae5a9e9a)


## Conclusion
The clustered data provides valuable insights that can be used to tailor the delivery service and make informed decisions about new customers, ultimately improving the distributor's operations and customer satisfaction.

- Effect of Delivery Scheme Change: The customer segments identified through clustering can help the wholesale distributor determine which customers might react positively to a change in the delivery service. By understanding the types of establishments each segment represents, the distributor can make informed decisions. For example, restaurants and cafes (which might fall into one segment) may value more frequent deliveries for freshness, while retailers (in another segment) might prefer fewer deliveries to reduce costs.

- Labeling New Customers: The customer segments can be used as an engineered feature for the data, allowing the distributor to classify new customers into the appropriate segment. This can be done using a supervised learning approach, where the original customers' spending data is used as input and the customer segment as the target variable. Once trained, this model can predict the segment for new customers based on their spending estimates.

- Visualizing Underlying Distributions: By reintroducing the 'Channel' feature (Hotel/Restaurant/Cafe or Retail) and plotting the data points in the reduced PCA space, we can see how each data point is labeled. This visualization helps us understand how well the clustering algorithm has grouped similar types of establishments together.


