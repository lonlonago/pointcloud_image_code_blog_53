#  Function overview 

   This example shows how to estimate the rigid transformation between two point clouds. In this example, feature extraction and matching are used to significantly reduce the number of points required for estimation. After extracting a fast point feature histogram (FPFH) from a point cloud using the extractFPFHFeatures function, use the pcmatchfeatures function to search for matches in the extracted features. Finally, use the estimateGeometricTransform3D function and matching features to estimate the rigid transformation. 

#  Second, the official website code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574532957
  ```  
#  III. Display of results 

 ![avatar]( 495725660a604327a67026c1ac0efaba.png) 

#  IV. Application examples 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574532957
  ```  
 The results show that the experimental experience 

   The algorithm is slightly less efficient than C++ and Python. 

#  V. Reference links 

 matlab点云工具箱——Estimate Transformation Between Two Point Clouds Using Features 



--------------------------------------------------------------------------------

#  I. Overview of algorithms 

   First, the intrinsic shape feature (ISS) feature points are extracted from the point cloud to be registered, then the FPFH feature descriptor of the ISS feature point is calculated, and then the transformation matrix of the point cloud is calculated according to the FPFH feature descriptor of the feature point, and the transformation matrix is used to complete the point cloud registration. 

##  2. Main functions 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574568721
  ```  
#  III. Display of results 

 ![avatar]( a81632ce3c514a819b8f03b80c8ba0c2.png) 

#  Fourth, a warning!!! 

   Copy and paste the code and run it directly. Don't read other content on the blog. If you report an error, you can directly open "Why did I report an error, what kind of garbage code is this"??? detectISSFeatures is a new function in matlab2022a and above, so why do some bosses make mistakes?? Why ask?????  



--------------------------------------------------------------------------------

#  Function overview 

##  1. Algorithm overview 

 ![avatar]( 4f77a57e7a704a9280c8c55260fc5448.png) 

   This diagram shows the workflow for point cloud registration using the FGR algorithm.  

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574568583
  ```  
   Returns a rigid transformation that registers a moving point cloud to a fixed point cloud. This function uses a fast global registration (FGR) algorithm based on FPFH features to match point clouds. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574568583
  ```  
 In addition, the root mean square error of the Euclidean distance of the registration result is returned. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574568583
  ```  
 Specifies the maximum number of iterations for the FGR algorithm, as well as any combination of parameters from the previous syntax. 

##  3. Input and output parameters 

>  Use skills:

To improve the accuracy and efficiency of registration, use the pcdownsample function to downsample the point cloud before using the pcregisterfgr function. For point clouds extracted by onboard mobile measurement systems, performance and accuracy can be improved by using pcfitplane or segmentGroundFromLidarData removing the ground before registration. To merge more than two point clouds, use the pccat function instead of the pcmerge function. 

##  4. References 

>  [1] Zhou Q Y , Park J , Koltun V . Fast Global Registration[J]. 2016 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574568583
  ```  
#  III. Display of results 

 ![avatar]( 263b80f2e390470d83f99a28b4c2c4ca.png) 

#  Fourth, a warning!!! 

   Copy and paste the code and run it directly. Don't read other content on the blog. If you report an error, you can directly open "Why did I report an error, what kind of garbage code is this"??? pcregisterfgr is a new function in matlab2022b and above, so why do some bosses make mistakes?? Why ask?????  



--------------------------------------------------------------------------------

#  I. Overview of algorithms 

   First, the intrinsic shape feature (ISS) feature points are extracted from the point cloud to be registered, then the FGR global registration is performed based on the ISS feature points, and finally the original point cloud is registered using the transformation matrix. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957453187
  ```  
#  III. Display of results 

 ![avatar]( d75a4b56cec747e3a857e41d62ba8908.png) 

#  Fourth, a warning!!! 

   Pcregisterfgr is a new function in matlab2022b and above.  



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm overview 

   The basic idea is to calculate the transformation matrix by randomly sampling a certain number of point pairs, and then use the transformation matrix to transform the source point cloud into the target point cloud coordinate system to calculate the error between the transformed point cloud and the target point cloud. If the error is less than a certain threshold, these point pairs are determined to be inner points, otherwise they are determined to be outer points. Then randomly sample a set of point pairs and repeat the above steps until the optimal transformation matrix satisfying a certain proportion of inner points is found. 

##  2. Implementation process 

   The implementation steps of the RANSAC algorithm in this paper are as follows: 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574557511
  ```  
#  III. Display of results 

 ![avatar]( 6ca4297ccc544275a95b5070ec8fb03e.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

   First, the elevation extremum (including the maximum and minimum elevation) of the point cloud is obtained according to the Z-axis direction, and then the elevation is normalized to the range of 0~ 255. Finally, the colormap color rendering function in matlab is used to color and save the rendering result to the point cloud. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574591741
  ```  
#  III. Display of results 

 ![avatar]( b948507cb33c43e9839208847a2407a3.png) 

#  IV. Optional color types 

 ![avatar]( a786ace6d4434522910492b281ccca04.png) 

#  CloudCompare 

 ![avatar]( 20201231103449200.gif) 

 Related implementation operations in CloudCompare software  

#  VI. Reference link 

 colormap 



--------------------------------------------------------------------------------

#  I. Overview of algorithms 

   ① Establish a horizontal grid according to the measurement range and number each grid unit; ② Project all data points vertically onto the grid; ③ Edge detection algorithm extracts boundaries. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574517374
  ```  
#  III. Display of results 

 ![avatar]( a055aee9229f4dd6935a34f58f238f99.png) 

 Point cloud, point cloud contour edge  



--------------------------------------------------------------------------------

    This example demonstrates how to transform an unorganized point cloud into an organized form using spherical projection. 

##  1. Introduction 

   3-D LiDAR point clouds are often represented as a set of Cartesian coordinates. In addition, point clouds contain other information such as intensity and RGB values. Unlike the distribution of image pixels, the distribution of LiDAR point clouds is often sparse and irregular. Processing this sparse data is inefficient. To obtain a compact representation, a LiDAR point cloud can be projected onto a sphere to create a dense grid-based representation called an organized form [1]. To learn more about the differences between organized and unorganized point clouds, see: Lidar Processing Overview. An organized point cloud is required for ground extraction and critical point detection methods. In addition, to use deep learning segmented networks such as SqueezeSegV1, SqueezeSegV2, RangeNet ++ [2], and SalsaNext [3], you need to convert an unorganized point cloud to an organized point cloud. For an example demonstrating how to use an organized point cloud for deep learning, see Lidar Point Cloud Semantic Segmentation Using SqueezeSegV2 Deep Learning Network. 

##  2. LiDAR sensor parameters 

   To convert an unorganized point cloud to an organized format using spherical projection, you must specify the parameters of the lidar sensor used to create the point cloud. Determine the parameters to specify by referencing the sensor's data table. The following parameters can be specified. 

##  3. Ouster OS-1 sensor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574588082
  ```  
 result display  

 ![avatar]( e5bc6df1d43741d2afe428900d40c675.png) 

##  4. Velodyne sensor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574588082
  ```  
 result display   

##  5. Pandar sensor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574588082
  ```  
 ![avatar]( 19b97c1ea9d14acaa84e12a634bf87be.png) 

##  6. Auxiliary functions 

 Use the convertUnorgToOrg function to find the pixel coordinates of all projected images. The function follows these steps: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574588082
  ```  
##  7. References 

>  [1] Wu, Bichen, Alvin Wan, Xiangyu Yue, and Kurt Keutzer. “SqueezeSeg: Convolutional Neural Nets with Recurrent CRF for Real-Time Road-Object Segmentation from 3D LiDAR Point Cloud.” In 2018 IEEE International Conference on Robotics and Automation (ICRA), 1887-93. Brisbane, QLD: IEEE, 2018. https://doi.org/10.1109/ICRA.2018.8462926. [2] Milioto, Andres, Ignacio Vizzo, Jens Behley, and Cyrill Stachniss. “RangeNet ++: Fast and Accurate LiDAR Semantic Segmentation.” In 2019 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 4213-20. Macau, China: IEEE, 2019. https://doi.org/10.1109/IROS40897.2019.8967762. [3] Cortinhal, Tiago, George Tzelepis, and Eren Erdal Aksoy. “SalsaNext: Fast, Uncertainty-Aware Semantic Segmentation of LiDAR Point Clouds for Autonomous Driving.” ArXiv:2003.03653 [Cs], July 9, 2020. https://arxiv.org/abs/2003.03653. [4] Kim, Jaden. “UCS - Ouster LiDAR.” Accessed December 22, 2020. https://data.ouster.io/downloads/datasheets/datasheet-gen1-v1p13-os1.pdf. [5] Velodyne Lidar. “HDL-64E Durable Surround Lidar Sensor.” Accessed December 22, 2020. https://velodynelidar.com/products/hdl-64e/. [6] “PandaSet Open Datasets - Scale.” Accessed December 22, 2020. https://scale.com/open-datasets/pandaset. [7] “Pandar64 User Manual.” Accessed December 22, 2020. https://hesaiweb2019.blob.core.chinacloudapi.cn/uploads/Pandar64_User’s_Manual.pdf. 

##  8. Reference link 

 matlab点云工具箱——Unorganized to Organized Conversion of Point Clouds Using Spherical Projection 



--------------------------------------------------------------------------------

#  I. DBSCAN 

##  1. Effect display 

 ![avatar]( b85dafbdc7004afe9c693913910c7803.png) 

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574557955
  ```  
    The DBSCAN algorithm is used to cluster the observations in the data matrix. dbscan clusters the observations (or points) based on the threshold of the neighborhood search radius and the minimum number of neighbors required to identify the core points. The function returns an index vector containing the cluster index for each observation. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574557955
  ```  
    Specify additional options for a parameter using one or more name-values. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574557955
  ```  
    You can also return a logical vector corepts containing the core points identified by dbscan. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574557955
  ```  
#  III. Display of results 

##  1. Primitive point cloud 

 ![avatar]( 639e8b8ea6de4cda909d3d63f284fcc3.png) 

##  2. Clustering results 

 ![avatar]( 0d160f42103540b3abd1766b023e0cfd.png) 

##  3. Denoising results 

 ![avatar]( c8304a4d255440d38f68e488bfaa9a06.png) 



--------------------------------------------------------------------------------

#  First, the sampling method 

##   1. Voxel downsampling 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574578032
  ```  
 Use a voxel filter to return to the downsampled point cloud. 

##   2. Random downsampling 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574578032
  ```  
 Returns a downsampled point cloud with random sampling that does not require substitution. 

##   3. Non-uniform downsampling 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574578032
  ```  
 Uses a non-uniform voxel filter to return a downsampled point cloud. This method selects a random point from each box. If no normals are provided in the input point cloud, this method will automatically populate the Normal property in the ptCloudOut output. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574578032
  ```  
#  III. Display of results 

 ![avatar]( 2021060510215376.png) 

#  IV. Reference link 

 Matlab point cloud tool - pcdownsample 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   The effect of terrain on vegetation data can be eliminated using elevation normalization. The elevation normalization steps are as follows: 1. Use the groupsummary function to eliminate duplicate points on axes and axes, if any. 2. Use the scatteredInterpolant object to create an interpolation to estimate each ground point in the point cloud data. 3. Normalize the elevation of each point by subtracting the interpolated ground elevation from the original elevation. 

##  2. References 

>  [1] Thompson, S. Illilouette Creek Basin Lidar Survey, Yosemite Valley, CA 2018. National Center for Airborne Laser Mapping (NCALM). Distributed by OpenTopography. https://doi.org/10.5069/G96M351N. Accessed: 2021-05-14 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574526041
  ```  
#  III. Display of results 

 ![avatar]( b488dfe396434f5b8238487061d8eb91.png) 

#  IV. Test data 

 Link: https://pan.baidu.com/s/1R2zlom1iF8lUPpuJx6L-Aw Extraction code: yg1f 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   Farthest Point Sampling (FPS) is a method of sampling on a point cloud or surface, the purpose of which is to select a group of points with the largest interval from the point cloud or surface for subsequent processing or analysis. 

##  2. References 

>  [1] Hu Q , Yang B , Xie L , et al. RandLA-Net: Efficient Semantic Segmentation of Large-Scale Point Clouds[J]. 2019. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574579687
  ```  
#  III. Display of results 

 ![avatar]( a328732810ab4d4bb813643a79789522.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm overview 

   The point cloud is equally spaced slices along the axis, and the code extracts a 0.04m thick slice every 0.4m along the Z axis. 

##  2. Preview of results 

>  White is the original point cloud, purple is the sliced point cloud. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957454038
  ```  
#  III. Display of results 

 ![avatar]( 37e9dbd34b9c4156810f3666a47b43f7.png) 

#  IV. Relevant links 

 PCL point cloud is equally sliced along the coordinate axis 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Baidu Netdisk 

 Link: https://pan.baidu.com/s/1mL_iK3C8R8SEPc6SiOV16g Extraction code: 6zru 

#  First, read, write and save 

#  Second, the KD tree 

#  Point cloud filtering 

##  1. Commonly used filters 

##  2. Data smoothing 

#  IV. Fitting segmentation 

##  1. Point cloud fitting 

##  2. Point cloud segmentation 

#  Point cloud reconstruction 

#  Point cloud registration 

##  1. Rough registration 

##  2. Fine registration 

##  3. Point cloud transformation 

##  4. Characteristics and description 

#  Point clouds and images 

#  Eight, point cloud visualization 

#  Point cloud deep learning 

 Matlab2021b Added code auto-completion function matlab2020b matlab2021b  

#  X. Basic operations 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

   For the whole point cloud, the covariance matrix is constructed as: in the formula,; is the center point of all points in the point set. According to the formula, calculate the eigenvalues and eigenvectors of the covariance, where is the eigenvalue of, and; is the corresponding eigenvector. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574562620
  ```  
#  III. Display of results 

 ![avatar]( 28b2b88fad1742bcac41a54e611962b9.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

   For the obtained point cloud data, let the fitted plane equation be: the constraint condition is: the plane parameters can be obtained. At this time, to make the obtained fitted plane optimal, that is, to minimize the sum of squares of the distances from the adjacent points to the plane, that is, to satisfy: In the formula, it is the distance from any point in the point cloud data to this plane. To make, you can use matrix factorization to get. The derivation process is as follows: the average coordinates of all points are, then: formula (1) is subtracted from formula (4) to obtain: hypothesis matrix: column matrix: then formula (5) is equivalent to: ideally all points are on the plane, formula (6) holds; in practice, some points are outside the plane, and the purpose of fitting is to minimize the sum of the distances from all points in the plane, so the objective function is: The constraints are: 

  If singular value decomposition can be done: then: where: is a column matrix, and: because the diagonal element of is a singular value, assuming that the last diagonal element is the smallest singular value, then if and only if:, formula (10) can obtain the minimum value, that is, formula (7) holds. At this time: the optimal solution of the objective function (7) under the constraint condition (8) is: Therefore, the minimum value of is the minimum eigenvalue of the matrix, and the corresponding eigenvector is a plane parameter, which can be obtained by using the centroid. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957451394
  ```  
#  III. Display of results 

 ![avatar]( a0516ceff1a547a2acdb7a3edf2d51d9.png) 



--------------------------------------------------------------------------------

#  I. Overview 

##  1. Algorithm overview 

   The polyfit function is a polynomial curve fit. For polynomials, the polynomial coefficients are:. 

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574552484
  ```  
    Returns the coefficients of a polynomial of order, which is the best fit of the least squares method in the data. The coefficients in are arranged by power, and the length is. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574552484
  ```  
   It also returns a structure S that can be used as input to a polyval to obtain an error estimate. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574552484
  ```  
   Also returns, the latter is a two-element vector containing the centered and scaled values. Is mean (x), is std (x). When using these values, polyfit places the center of, at the zero value and scales to have the unit standard deviation  

   This centralization and scaling transformation can simultaneously improve the numerical properties of polynomials and fitting algorithms. 

#  Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574552484
  ```  
#  III. Display of results 

 ![avatar]( 5db7f396a8df4f4493dfdf5dd14f9e5b.png) 

#  IV. Parameter analysis 

##  input parameter 

 A warning message result when x has duplicate (or near duplicate) points or if x may require centralization and scaling. 

##  output parameter 

#  V. Reference links 

 polyfit 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

   The quadric surface equation is as follows: the least squares method is used to fit the local quadric surface, and the objective function is established as: the joint vertical equation (1) and the equation (2), the linear equation system is obtained, see the equation (3), the linear equation system is solved, and the local quadric fitting surface equation is obtained. 

##  2. References 

>  [1] Equation Xi, Sui Beginning of Spring, Zhu Haixiong. LiDAR point cloud thinning algorithm for highway survey design [J]. Bulletin of Surveying and Mapping, 2017 (10): 58-61 + 88. 

#  III. Code implementation 

##  1. Detailed process implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957454491
  ```  
##  2. Call function implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957454491
  ```  
#  IV. Display of results 

 ![avatar]( 3312ff2dbf0a424b9b114af8b9d56949.png) 

#  Test data 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957454491
  ```  


--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Calculation process 

   Space spherical equation: Formula (1) can be written as: let, then formula (2) is simplified as: write formula (3) in the form of a matrix, as shown in (4): solve the parameters to be obtained, substitute them, to obtain the coordinates of the spherical center of space and the radius of the spherical sphere. 

##  2. References 

>  Wang Hua, Hou Daishuang, Zhang Shuang, Gao Jingang. Spatial straightness detection of train axle [J]. Computer Applications, 2019, 39 (10): 2960-2965. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574533129
  ```  
#  III. Display of results 

 ![avatar]( 8ebe1a655cb844fbba2bd092b77f784e.png) 



--------------------------------------------------------------------------------

