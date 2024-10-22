# **Midterm 01 review**
  
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
### **Decision Tree**  
Supervised learning  
➩ Find the feature that is the most informative.  
➩ Split the training set into subsets based on this feature.  
➩ Repeat on each of the subset recursively until all features or labels in the subset are the same.  

### **Measure of Uncertainty**  
Let P0 be the fraction of items in a training with label 0 and P1 be the fraction of items with label 1.  
➩P0 = 0 and P1 = 1, vise versa, no uncertainty, the measure of uncertainty is 0.  
➩If both is 0/5, then the uncertainty is max, which is 1.  
Calculation: H = -p0 * log2(p0) - p1 * log2(p1)  

### **Entropy**  
K classters, Py is the fraction of the training set with label y,   
H(y) = -p1 * log2(p1) - p2 * log2(p2) - ... - pk * log2(pk)   
Conditional entropy is the entropy of the conditional distribution:  

### **Information Gain**   
The Entropy before the split - the Entropy after the split, I(y|x) = H(y) - H(y|x)  
The larger the Information Gain, the more info we know.   
Decision tree is jsut split the dataset the way that all have the most Information Gain, on and on  
Computation:  
![image](https://github.com/user-attachments/assets/67bc2527-d24e-401f-869e-8a5fa89c00d0)

    
### **Pruning**  
Decision trees can be pruned by replacing a subtree by a leaf when the accuracy on a validation set with the leaf is equal or higher than the accuracy with the subtree. This method is called Reduced Error Pruning: .  
➩ A validation set is a subset of the training set that is set aside when training the decision tree and only used for pruning the tree.  
➩ The items use to train the decision tree cannot be used to prune the tree.  

### **Random Forest**  
Use alot of tree and let them vote.  
there is no waight on each tree, each tree have the same weight.  

### **Adaptive Boosting**  
For the previous tree, is some part is misclassfied, then the next tree will be focused on the with-issue part.  
By repeating, there will be a sequency of trees and they will vote.  
  
Decision trees can also be trained sequentially. The items that are classified incorrectly by the previous trees are made more important when training the next decision tree.  
Each training item has a weight representing how important they are when training each decision tree, and the weights can be updated based on the error made by the previous decision trees. This is called AdaBoost (ADAptive BOOSTing): .  

























