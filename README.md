# Cryptocurrencies


This project uses machine learning to identify which cryptocurrencies are on the trading market and to better understand how cryptocurrencies can be grouped to create classifications for developing an investment product. 

Unsupervised machine learning algorithms are used as there is no known output. 

To group the cryptocurrencies, a clustering algorithm was chosen and the findings will be presented through data visualizations. 

Steps included in this project:

Data preprocessing. This step included in-depth data cleaning, such as removing null values and removing cryptocurrencies without coins mined. In addition, the encoding method "get_dummies()" was used for the text features and StandardScaler() was used to standardize and transform the data.
Reducing data dimensions using PCA. In this step, a dataframe's dimensions was reduced to three principal components and a new dataframe was created.
Clustering cryptocurrencies using K-means. During step, an elbow curve was created to find the best value for the clustering groups and a K-means algorithm was used to predict the K clusters for the cryptocurrencies’ data.
Visualizing results. In this final step, three types of figures were used: a 3D scatter plot to visualize the three PCAs, a hvplot.table to visualize all the current tradable cryptocurrencies, and a 2D scatter plot to visualize "Total Coins Mined" vs. "Total Coin Supply" by coin name and clusters.
