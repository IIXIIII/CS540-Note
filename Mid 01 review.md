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
<img width="1132" alt="Screenshot 2024-10-22 at 5 00 19 PM" src="https://github.com/user-attachments/assets/3543cfc1-cc5a-4c81-9044-7ece8ef770f0">  
Find ways to do the split that mini the Gini Index.  
Make sure the node is as pure as possible so it could be either a yes or a no (binary, 0 or 1)  
**Divergence** like Gini, need to be as big as possible. THe biger the value, the pure the node.  
<img width="1469" alt="Screenshot 2024-10-22 at 5 06 14 PM" src="https://github.com/user-attachments/assets/c2c3b735-506e-430b-baf8-2cddf9fdee06">  
<img width="1470" alt="Screenshot 2024-10-22 at 5 07 21 PM" src="https://github.com/user-attachments/assets/2ef9f633-f402-4e5b-abc0-342fdb0cf68d">  
The Divergence of the age split is greater than the gender split, Leading to a more pure node, therefore it is batter.  




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

## **L7**  
### **Linear Classifier**  
Draw a straight line among the two types(label) of documents.  
The test doc is labeled based on which side of the line it lies.  
W0 + W1X1 + W2X2 = b  (for a two dim)
where the doc contain 2 features, x1 and x2  
w for weight, decide the orientation of the line.  
w0 (or Bias): distance from the origine, other w for the slope of the line  
We use the **perception Alg** to adjust.  

### **Perceptron Algorithm**  
The **learning rate** controls how fast the weights are updated.  
**learning rate** is usually constant, ussually 1.  
**learning rate** can also be a function of time.  
![image](https://github.com/user-attachments/assets/e7f93319-bc9b-4d59-9d04-ab1bdab698ad)

![image](https://github.com/user-attachments/assets/8206dab1-9630-4246-b7e2-2938f3a26200)  

### **Activation Functions**  closely related with the **Neuro Network**
This function an be nonlinear: sigmoid,ReLU (work well in practice),....  
Sometimes the ReLU doesn't work because it block the negative input, the **Leaky ReLU** and **ELU** sometimes can fix this problem.  
Usually act like a middle layer of a Neuro network that cam be linear or non-linear,  
  
Sometimes there are **Vanishing Gradient Problem**, because layers of neuro network reduce info and no Gradient no learning.  
To fix this we use **Activision Functions** that dont squeezes information.  
<img width="1465" alt="Screenshot 2024-10-22 at 5 27 42 PM" src="https://github.com/user-attachments/assets/0e98c5fa-abcf-4387-86ff-86fac45c73a4">  

### **Loss Functions** which need **Linear Regression**  


###**Linear Regression**  
The point (or goal) of ML or Regression is to drow a line the pass through a cloud of points.  
<img width="1115" alt="Screenshot 2024-10-22 at 5 33 57 PM" src="https://github.com/user-attachments/assets/b449e5fb-3e87-4749-bb60-31a0a3ee7019">   
The first two work, since the coeff is linear, but the second doesn't work for linear regression.  



























