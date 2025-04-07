# DASM-LIO

## DASM-LIO: Fast and Accurate LiDAR-Inertial Odometry with Distribution-Adaptive Surfel Maps

## 1. Introduction
In the field of LiDAR-inertial odometry, many works have proposed using surfel maps instead of point clouds, as surfels fitted from a large number of points provide more accurate plane estimations. These approaches typically segment the point cloud into voxels and fit planes to the points within these voxels. However, fixed-grid voxels struggle to adapt to the irregular distributions in point clouds, often resulting in improper segmentation and reduced plane estimation accuracy. To address this issue, we propose in this paper a distribution-adaptive surfel map (DASM). DASM adaptively generates uniformly distributed sampling points on object surfaces from on each scan to extract the surfels, minimizing the risk of improper segmentation. Additionally, these sampling points can be arranged compactly to capture finer-grain details. We assume a 3D Gaussian point distribution for the surfel extraction, and efficiently integrate newly added points through incremental updates. These sampling points are organized in an ordered manner using voxel hashing to enable fast map access. We designed a more efficient neighborhood search method to accelerate both mapping and map queries. Experiments on various open-source datasets show that our method achieves superior accuracy and computational efficiency compared to relevant baselines. Our code is publicly available on GitHub at https://github.com/Hanhui-Liu/DASM-LIO to facilitate further research. 

<div align="center">
    <img src="pics/mars03_gaussian.jpg" width = 100% >
</div>
