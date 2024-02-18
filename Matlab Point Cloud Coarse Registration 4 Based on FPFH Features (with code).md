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

