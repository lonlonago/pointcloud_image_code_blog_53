#  First, the principle of the algorithm 

   For the obtained point cloud data, let the fitted plane equation be: the constraint condition is: the plane parameters can be obtained. At this time, to make the obtained fitted plane optimal, that is, to minimize the sum of squares of the distances from the adjacent points to the plane, that is, to satisfy: In the formula, it is the distance from any point in the point cloud data to this plane. To make, you can use matrix factorization to get. The derivation process is as follows: the average coordinates of all points are, then: formula (1) is subtracted from formula (4) to obtain: hypothesis matrix: column matrix: then formula (5) is equivalent to: ideally all points are on the plane, formula (6) holds; in practice, some points are outside the plane, and the purpose of fitting is to minimize the sum of the distances from all points in the plane, so the objective function is: The constraints are: 

  If singular value decomposition can be done: then: where: is a column matrix, and: because the diagonal element of is a singular value, assuming that the last diagonal element is the smallest singular value, then if and only if:, formula (10) can obtain the minimum value, that is, formula (7) holds. At this time: the optimal solution of the objective function (7) under the constraint condition (8) is: Therefore, the minimum value of is the minimum eigenvalue of the matrix, and the corresponding eigenvector is a plane parameter, which can be obtained by using the centroid. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957451394
  ```  
#  III. Display of results 

 ![avatar]( a0516ceff1a547a2acdb7a3edf2d51d9.png) 

