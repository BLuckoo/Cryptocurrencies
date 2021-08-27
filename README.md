# Cryptocurrencies

## Overview

This project uses machine learning to identify which cryptocurrencies are on the trading market and to better understand how cryptocurrencies can be grouped to create classifications for developing an investment portfolio. 

Unsupervised machine learning algorithms are used as there is no known output. In unsupervised machine learning technique in which the users do not need to supervise the model. Instead, it allows the model to work on its own to discover patterns and information that was previously undetected. 

To group the cryptocurrencies, a clustering algorithm was selected and the findings will be presented through data visualizations. 

## Analysis & Models

**The technical analysis to produce the visualizations are as follows:**

1.  ***Preprocessing the Data***: 
    
    -  Prior to analysing the data and creating models, the dataset needs to be prepared to enhance the quality of data to promote the extraction of meaningful insights.
    -  Data preprocessing refers to the technique of cleaning and organizing the raw data to make it suitable for building and training Machine Learning models. 
    -  It is a data mining technique that transforms raw data into an understandable and readable format. 
    
    In this project, data cleaning such as removing null values and removing cryptocurrencies without coins mined was performed. In addition, the encoding method "get_dummies()"       was used to convert text features into binary format and StandardScaler() was used to standardize and transform the data.
    
    The following is an extract of the original dataset that was converted to a DataFrame. It contained 1,252 rows and 6 columns of data.
    
    <p align="center">
    <image src= "https://user-images.githubusercontent.com/82583576/131057477-27e7784a-8a3b-4061-9fac-d63ce562940b.png"
    </p>

    
    Following the process of cleaning, dropping rows with null data, converting columns containing text to binary format, the DataFrame used for the model contained 532 rows and 98 columns.
    
    <p align="center">
    <image src= "https://user-images.githubusercontent.com/82583576/131057974-1d374e99-f46c-42bf-8ef4-5b178dd18421.png"
    </p>
                 
      
        
2.  ***Reducing data dimensions using Principal Components Analysis (PCA)***
        
    - Dimensionality reduction refers to techniques for reducing the number of input variables in training data.
    - Fewer input dimensions often means correspondingly fewer parameters or a simpler structure in the machine learning model, referred to as degrees of freedom. A model with too many degrees of freedom is likely to overfit the training dataset and may not perform well on new data.
    - Dimensionality reduction is a data preparation technique performed on data prior to modeling. It might be performed after data cleaning and data scaling and before training a predictive model.
             
    For this project, the DataFrame was reduced to three (3) principal components using the PCA method.
        
    <p align="center">    
    <image src="https://user-images.githubusercontent.com/82583576/131058631-5dbd6d87-af37-4f08-855d-f1978a1efcdc.png"
    </p>
        
3.  ***Clustering cryptocurrencies using K-means***
        
    -  Clustering is an important concept when it comes to unsupervised learning. It mainly deals with finding a structure or pattern in a collection of uncategorized data.  
    -  K means is an iterative clustering algorithm which helps to find the highest value for every iteration. 
    -  Initially, the desired number of clusters are selected. In this clustering method, the data points are clustered into k groups. 
    -  Unsupervised Learning Clustering algorithms will process the data and find natural clusters(groups) if they exist in the data. The number of clusters can be defined in the  algorithms. This allows to adjust the granularity of these groups. A larger k means smaller groups with more granularity in the same way. A lower k means larger groups with less granularity.
    -  In k-means clustering, each group is defined by creating a centroid for each group. The centroids are the center of the cluster, which captures the points closest to them and adds them to the cluster.
    
    To find the K-means value for the model, an elbow curve was created and a K-means algorithm was used to predict the K clusters for the cryptocurrencies’ data.

    <p align="center">
    <image src="https://user-images.githubusercontent.com/82583576/131060235-451f633f-068f-4f8d-a80b-cf0e915ac6dc.png"
    </p>       
    
    <p align="center">    
    <image src="https://user-images.githubusercontent.com/82583576/131060311-3786f384-ecbc-4e4b-bdd5-66fb98ad3d94.png"
    </p>

    - From the Elbow curve, the K-value of 4 was used in the model. The optimal K-value is the x-axis value where the curve shows a "marked" tendency towards a straight line.   
        
4. ***Visualizing results***

   - To visualize the results of the model, the following figures were used:
        
        - 3-D scatter plot of the three Principal Components showing the clusters
            - *This plot uses the three principal compenents obtained through the PCA algorithm as data*
            - *It clearly shows that BitTorrent is in a class by itself*
        
        <p align="center">
        <image src="https://user-images.githubusercontent.com/82583576/131062257-b8ecfe1c-2640-4ce0-817a-825d949e6242.png"
        </p>
 
   
            
            

        
        - The following is a snapshot of a hvplot.table to visualize all the current tradable cryptocurrencies.
            
        <p slign="center">
        <image src="https://user-images.githubusercontent.com/82583576/131061791-66cc9c72-8088-41d8-b621-b72084466d3c.png"
        </p>
              
                  
            
        - A 2D scatter plot to visualize "Total Coins Mined" vs. "Total Coin Supply" by coin name and clusters.
            
        <p align="center">
        <image src="https://user-images.githubusercontent.com/82583576/131061989-b5bbbe56-45d1-4b50-8bd7-f68faf43bc97.png"
        </p>

            
## Summary 
            
   - A total of 532 cryptocurrencies have been classified into four different classes based on similarities of their features.
   - Each class should be further analyzed to determine their returns and risks factors so that a proper portfolio can be presented to the investment bank's clients.   
