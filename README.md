# International Market Analysis for Chicken Meat Sales

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

### PCA Method:
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

### Clustering Methods:
Implementation of Kmeans for data partitioning.
Determination of the optimal number of clusters using the elbow method.
Cluster characterization with boxplots.
Usage of Hierarchical Clustering (CAH) to explore data structure.

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/clusters_kmeans.png)

![Texte alternatif](https://github.com/MelvinDerouck/Market-survey-for-a-food-processing-company/blob/main/Viz/dendrogram.png)


### Cluster Characterization:
Comparison of results between Kmeans and CAH using a heatmap.
Validation of Kmeans results.
Visualization of country importers with a GeoMap.

### Scoring and Results:
Application of scoring in two scenarios: ecological and social vs business.
Identification of the top three countries in each scenario.
Flexibility to adjust weights based on business needs.

# Conclusion:
This project provides a strategic market analysis for a chicken meat sales company, utilizing advanced techniques like PCA and clustering. The results offer a nuanced understanding of international markets, allowing the company to tailor its approach for successful expansion.

