# Midterm 01 review
  
## **L3**  
### **High Dimensional Data**  
    Datasets with a large number of features.    
    Leading to  
      curse of dimensionality  
      overfitting  
Need for effective feature selection and **dimensionality reduction** techniques.
  
### **Principal Component Analysis** 
    Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms high-dimensional data into a lower-dimensional space while preserving as much variance as possible, helping to simplify the data for analysis and visualization.  
**Projected variance**  
    goal is to maximize the projected variance along the selected principal components. This means you want to choose the directions that capture the most variability in the data, as a higher projected variance indicates that the principal component effectively represents the underlying structure and patterns in the dataset. By focusing on components with large projected variance, you can retain the most important information while reducing dimensionality.  
**Direction**  
    A unit vactor that represent the direction of the **principal components**
  
## **L4**  

###  **Hierarchical Clustering**
    ➩ Start with each items as a cluster.  
    ➩ Merge clusters that are closest to each other.  
    ➩ Result in a binary tree with close clusters as children.   

### **Distance between Points ** 
**Euclidean distance** (also called L2 distance): sqrt distance  
**Manhattan distance** (L1): X+Y distance  
**Chebyshev distance** (Linfinit): max(X,y)   

### **Distance between Clusters ** 
**single linkage distance**: the shortest distance from any item in one cluster to any item in the other cluster  
**complete linkage distance**: the longest distance ~  
**average linkage distance**: the average distance from any item in one cluster to any item in the other cluster    

### **Number of Clusters**  
depend on casesS  

## **L5**  
### **K Means Clustering**  
K-means clustering (2-means, 3-means, ...) iteratively updates a fixed number of cluster centers  
➩ Start with K random cluster centers.  
➩ Assign each item to its closest center.  
➩ Update all cluster centers as the center of its items.  

### **Total Distortion**  
Measure of how well the data points are clustered around their centroids.  
It quantifies the compactness of the clusters and is calculated as the sum of the squared distances between each data point and its assigned centroid.  
Calculation: aqr(Euclidean distance between pt and center) add up.  

### Initial Clusters  
➩Random chosen  
➩The first cluster center can be a random item, the second cluster center can be the item that is the farthest from the first item, the third cluster center can be the item that is the farthest from the first two items, ...  

### **K Nearest Neighbor**  

### **Training Set Accuracy**  
  

## **L6**  


















