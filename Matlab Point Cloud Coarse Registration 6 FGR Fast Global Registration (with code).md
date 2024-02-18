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

