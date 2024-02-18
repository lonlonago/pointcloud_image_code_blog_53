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

