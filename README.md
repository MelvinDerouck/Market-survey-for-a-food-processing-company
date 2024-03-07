# Market Analysis for Chicken Meat Sales company

## Project Overview:
This project focuses on conducting a comprehensive market analysis for a chicken meat sales company aspiring to expand its operations internationally. 

Leveraging Python, Principal Component Analysis (PCA), and clustering techniques, the project aims to identify key insights and opportunities in the target markets.

## Methodology:
Utilized Principal Component Analysis (PCA) for data dimensionality reduction.

Clustering with Kmeans and Hierarchical Clustering (CAH) to form groups of countries based on similar characteristics.

Cluster characterization and application of a scoring system in two scenarios to select the three most relevant countries.

### Data Cleaning:
Focuses on ensuring data quality for project usability. The files used in the project include:

"disp_alim" file: Information on food imports and exports, food availability by country and type. Filtered for "Poultry Meat."

"population" file: Data on the number of inhabitants per country for the year 2017.

"pib" file: GDP information in US$ per capita for the year 2017.

"distance" file: Distances in km between each country, filtered to include only data related to the distance from France as the point of origin.

After merging these datasets, the resulting dataframe contains information for 163 countries, providing a comprehensive basis for further analysis.

## PCA Method:
Principal Component Analysis (PCA) is employed to simplify dataset complexity by identifying essential trends, referred to as principal components.

After standardizing numerical data, the model is applied, and the explained variance for each component, along with the cumulative percentage, is calculated. A "scree plot" visually displays the cumulative explained variance by the number of principal components.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/éboulis%20des%20valeurs%20propres.png)

In this case, the decision is made to use two principal components, with CP1 representing 29% and CP2 representing 20%, totaling 49% of the variance.

A scatter plot of the first factorial plane, using Principal Component Analysis (PCA) with CP1 and CP2, helps visualize countries with similar characteristics in terms of economic and demographic factors. Continents are distinguished by colors, revealing regional patterns.

Four distinct points on the plot represent countries with notably high values in certain variables (population, GDP). Despite not being outliers, these countries are economic powerhouses with different cultures, or geographically distant from France...

To avoid bias in clustering results, especially with K-means sensitivity to outliers, these four countries are excluded from the dataset used in the study.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/premier%20plan%20factoriel%20avec%20continents.png)

The correlation circle in Principal Component Analysis (PCA) simplifies the understanding of data dispersion on the factorial plane. Arrows represent variables, with their direction and length indicating contribution to each principal component. 

In our analysis, 'Population' strongly correlates positively with the second principal component, while export and import variables show strong negative correlation with the first. CP1 captures economic and trade-related information, while CP2 is associated with 'Population' and 'Distance'.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/cercle%20corr.png)

## Clustering Methods:
Clustering method partitions data into clusters based on their characteristics, helping group countries based on similarities in market indicators. The analysis utilizes the first two principal components from PCA.

### K-Means

Each data point is assigned to the cluster whose center (centroid) is closest. The Elbow Method determines the optimal number of clusters by showing the sum of squared distances from data points to their nearest centroids for different cluster counts. 

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/coude.png)

In this case, the elbow point suggests choosing 4 clusters (third dot).

The Cluster Scatter Plot represents data projected in a two-dimensional space, with each point colored based on its membership in one of the 4 clusters, along with their centroids.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/clusters_kmeans.png)

At first glance, countries in the green and purple clusters appear balanced and compact in terms of numbers. 

In contrast, individuals in the blue and pink clusters are fewer in number and more dispersed.

Now we can focuses on understanding the characteristics of different clusters obtained through K-means clustering. After applying K-means to the original dataset, the means of each variable across the four clusters are displayed. Cluster "2" is of particular interest, representing countries with relatively high averages across all variables, especially in import and export values, indicating active involvement in trade.

The clusters are named as "Very Insignificant," "Insignificant," "Significant," and "Very Significant." 
Here, a silhouette score of 0.68 is achieved, indicating a good score. The clusters appear to be coherent and well-separated. However, there is still room for improvement.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/boxplot%20PIB$%20k-means.png)

Boxplots further characterize the clusters, with the GDP boxplot showing low values for the "Very Insignificant" and "Insignificant" clusters, high values with variance for the "Significant" cluster, and relatively high and consistent values for the "Very Significant" cluster. The Imports boxplot indicates low medians and variance with outliers for the "Very Insignificant," "Insignificant," and "Significant" clusters, while the "Very Significant" cluster exhibits significantly higher import values.

This analysis can be extended to other variables for a comprehensive characterization of each cluster.

Projection on the First Factorial plane aims to validate K-means clusters and understand cluster attributes using the correlation circle. The well-separated clusters, notably "Very Significant" and "Significant" on the right side of the plot, align with high economic and trade-related characteristics (imports, exports, GDP per capita). This alignment reinforces the coherence of the clusters, validating the success of the K-means application.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/Projection%20premier%20plan.png)

Here is the 8 country in the "Trés pertinent" cluster : 

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/Clusters%20kmeans.png)

### CAH
The dendrogram visually illustrates the hierarchical cluster formation. Each line represents cluster fusion, with height indicating dissimilarity. 

The choice of cluster number (here, 4) considers both visual representation and business needs. Similar to K-means, clusters formed by Hierarchical Agglomerative Clustering (CAH) were characterized and renamed accordingly (e.g., "Insignificant").

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/dendrogram.png)

The Davies-Bouldin Index, evaluating clustering quality, yielded a score of 0.82, indicating a moderate level of quality. A score of 0 signifies perfect clustering. This suggests room for improvement, emphasizing the importance of employing multiple clustering methods and comparing results.

This table presents the final results of CAH, with countries identified in the "Trés pertinent" cluster. The final list consists of 7 countries, compared to 8 with K-means :

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/Clustering%20CAH.png)

## Clusters Characterization:
Heatmap is used to compare the results of the kmeans & CAH clustering :

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/heatmap%20clusters.png)

Lighter shades indicating higher numbers. Consensus exists in the "Very Insignificant" cluster (72), while in the "Very Significant" cluster, identified by both methods, there are 7 countries. Despite one discrepancy, the highly similar results led to keeping K-means for the study due to its acceptable silhouette score.

## Scoring and Results:
In this section, we assign weights to variables to create an ordinal ranking of the 8 countries based on obtained scores and identify the top 3 most relevant countries. Two scenarios are defined for flexibility:

**Eco-Social Scenario:** Higher weights given to distance and population variables. The table reveals the top 3 countries with the highest scores.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/score%20écolo.png)

**Business Scenario:** Higher weights assigned to GDP and imports variables. Germany consistently scores high, and the Netherlands secures the 2nd position in both scenarios. The 3rd position is occupied by the UK in the Eco-Social scenario and Japan in the Business scenario.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/score%20business.png)

These weights can be easily adjusted based on actual business needs.

