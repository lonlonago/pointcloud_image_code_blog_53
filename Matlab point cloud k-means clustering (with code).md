#  I. Kmeans 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574563188
  ```  
    Performs k-means clustering to divide the observations of the n × p data matrix X into k clusters and returns an n × 1 vector (idx) containing the cluster index for each observation. The rows of X correspond to points and the columns correspond to variables. By default, kmeans uses the Euclidean distance-squared metric and initializes the cluster centers with the k-means ++ algorithm. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574563188
  ```  
     Further returns the cluster index by one or more additional options specified by the Name, Value to the group parameter. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574563188
  ```  
    Returns the positions of k cluster centroids in the k × p matrix C. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574563188
  ```  
    Returns the sum of the distance from the points in the cluster to the centroid in the k × 1 vector sumd. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574563188
  ```  
    Returns the distance from each point to each centroid in an n × k matrix D. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574563188
  ```  
#  III. Display of results 

##  1. Primitive point cloud 

 ![avatar]( c83a1d21dec14407b6d3c10430986944.png) 

##  2. Clustering results 

 ![avatar]( b6a9ac3c4a214e96aa2f8b3d539d6d59.png) 

