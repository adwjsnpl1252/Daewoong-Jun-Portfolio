# Vancouver Crime Analysis And Clustering Project Overview

* Analyzed the Vancouver crime dataset to discover more about the crime that occurred in Vancouver from 2003 to mid-2017 and find some efficient solutions to reduce the crime.
* Explored the dataset with bar charts, heatmaps, scatterplots, and line plots to identify how the neighborhoods, the time, and the type of crimes affect the crime rates.
* Built a model with KMeans Clustering to cluster the regions.
* Visualized the clusters as 2-Dimensionals with T-SNE.

![](/images/vancouverphoto.png)


## *About the Dataset :*
- Dataset from Kaggle, https://www.kaggle.com/wosaku/crime-in-vancouver. 'Crime in Vancouver', uploaded by Wilian Osaku.
- 530,652 records of crimes in Vancouver from 2003-01-01 to 2017-07-13.

## *Features :*
* TYPE -> Different types of crimes happened in Vancouver.
* YEAR -> Year of the crime recorded
* MONTH -> Month of the crime recorded
* DAY -> Day of the crime recorded
* HOUR -> Hour of the crime recorded
* MINUTE -> Minute of the crime recorded
* HUNDRED_BLOCK -> Generalized location of the crime activity
* NEIGHBOURHOOD -> Neighbourhood where the crime occured
* X,Y -> Coordinate values projected in UTM Zone 10
* Latitude,Longitude -> Coordinate values converted to Latitude and Longitude

## *Section 1: Exploratory Data Analysis*
* By plotting different types of bar charts and line plots to visualize how the crime rates had altered over time.
* Distplot to identify the mean number of cases per day and pie charts to explore the ratios between each type of crimes.
* Looked more in-depth on 'Theft From Vehicle' crime as it was the major crime occurred in Vancouver over that 13 years.
* By using scatterplots, we can visualize the severity of crime in each neighborhood.
* Heatmaps to illustrate at which month,day or hour the crime got more serious. By using these heatmaps, we can able to find more efficient solutions to reduce the crime rates.
* Here are some highlights:

![](/images/van_crim_year.png)
![](/images/Vancouver_Crime.jpg)
![](/images/van_distplot.png)
![](/images/van_pie.png)
![](/images/van_total_crime.png)
![](/images/van_crime_map.png)
![](/images/van_heatmap.png)
![](/images/van_heatmap2.png)

## *Section 2: KMeans Clustering*
* By using label encoder from sklearn.prepreocessing, converts strings to specific integers, and scale the dataset by standard scaler.
* By using 'The Elbow Method', find the optimal number of clusters.
* After determining the optimal number of clusters, use the KMeans Clustering to separate into different clusters.
* Lower the dimensions of clusters to 2-Dimensionals for visualization with T-SNE.
* Explore each cluster to classify which cluster has the neighborhoods with the most criminal cases, the least, and the rest.
* Here are some highlights :

![](/images/cluster0.png)
![](/images/cluster1.png)
![](/images/cluster2.png)


## Conclusion :

* Based on the data analysis and KMeans clusterings, we can find some solutions on reducing the crime rates in Vancouver :
  * The government should deploy more police officers with more frequent patrols in the neighborhood in cluster 1 and 2.
  * Increase the patrols frequency during the afternoon and night time as most crimes occurred at this time. Especially on Friday and Saturday. Furthermore, Increase the patrol     rates during summer as there were more crime during summer compared to other seasons.
  * Increase the patrols near the residential areas at the morning.
  * As most of the crime recorded at every 30 minutes, therefore, the police officers should avoid duty shifts at these periods.
  * As auto theft is severe in every region of Vancouver. Hence the government should inform all the residents with vehicles to make sure that they should never leave anything     valuables inside the vehicles. In addition, make sure that the people leave the vehicles windows and door fully locked.
