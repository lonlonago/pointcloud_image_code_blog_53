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

