# Cryptocurrencies

## Overview

This project uses machine learning to identify which cryptocurrencies are on the trading market and to better understand how cryptocurrencies can be grouped to create classifications for developing an investment portfolio. 

Unsupervised machine learning algorithms are used as there is no known output. In unsupervised machine learning technique in which the users do not need to supervise the model. Instead, it allows the model to work on its own to discover patterns and information that was previously undetected. 

To group the cryptocurrencies, a clustering algorithm was chosen and the findings will be presented through data visualizations. 

## Summary of Analysis

**The technical analysis to produce the visualizations are as folows:**

1.  ***Preprocessing the Data***: 
    
    -  Prior to analysing the data and creating models, the dataset needs to be prepared to enhance the quality of data to promote the extraxtion of meaningful insights.
    -  Data preprocessing refers to the technique of cleaning and organizing the raw data to make it suitable for building and training Machine Learning models. 
    -  It is a data mining technique that transforms raw data into an understandable and readable format. 
    
    In this project, data cleaning such as removing null values and removing cryptocurrencies without coins mined was performed. In addition, the encoding method "get_dummies()" was used to convert text features into binary format and StandardScaler() was used to standardize and transform the data.
    
    The following is an extract of the original dataset that was converted to a DataFrame. It contained 1,252 rows and 6 columns of data.
    
    <p align="center">
    <image src= "https://user-images.githubusercontent.com/82583576/131057477-27e7784a-8a3b-4061-9fac-d63ce562940b.png"
    </p>

    
    Following the process of cleaning, dropping rows with null data, converting columns containing text to binary format, the DataFrame used for the model contained 532 rows and 98 columns.
    
    <p align="center">
    <image src= "https://user-images.githubusercontent.com/82583576/131057974-1d374e99-f46c-42bf-8ef4-5b178dd18421.png"
    </p>
                 
      
        
2.  ***Reducing data dimensions using Principal Compenents Analysis (PCA)***
        
    - Dimensionality reduction refers to techniques for reducing the number of input variables in training data.
    - Fewer input dimensions often means correspondingly fewer parameters or a simpler structure in the machine learning model, referred to as degrees of freedom. A model with too many degrees of freedom is likely to overfit the training dataset and may not perform well on new data.
    - Dimensionality reduction is a data preparation technique performed on data prior to modeling. It might be performed after data cleaning and data scaling and before training a predictive model.
             
 In this step, a dataframe's dimensions was reduced to three principal components and a new dataframe was created.
        
        
3.  ***Clustering cryptocurrencies using K-means***
    - During step, an elbow curve was created to find the best value for the clustering groups and a K-means algorithm was used to predict the K clusters for the cryptocurrencies’ data. Clustering is an important concept when it comes to unsupervised learning. It mainly deals with finding a structure or pattern in a collection of uncategorized data. Unsupervised Learning Clustering algorithms will process your data and find natural clusters(groups) if they exist in the data. You can also modify how many clusters your algorithms should identify. It allows you to adjust the granularity of these groups.

    -   K means it is an iterative clustering algorithm which helps you to find the highest value for every iteration. Initially, the desired number of clusters are selected. In this clustering method, you need to cluster the data points into k groups. A larger k means smaller groups with more granularity in the same way. A lower k means larger groups with less granularity.

The output of the algorithm is a group of "labels." It assigns data point to one of the k groups. In k-means clustering, each group is defined by creating a centroid for each group. The centroids are like the heart of the cluster, which captures the points closest to them and adds them to the cluster.

4. ***Visualizing results***
    - In this final step, three types of figures were used: a 3D scatter plot to visualize the three PCAs, a hvplot.table to visualize all the current tradable cryptocurrencies, and a 2D scatter plot to visualize "Total Coins Mined" vs. "Total Coin Supply" by coin name and clusters.
