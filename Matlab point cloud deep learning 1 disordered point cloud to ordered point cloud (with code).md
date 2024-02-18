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

