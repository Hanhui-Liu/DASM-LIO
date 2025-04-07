# DASM-LIO

## DASM-LIO: Fast and Accurate LiDAR-Inertial Odometry with Distribution-Adaptive Surfel Maps

## 1. Introduction
In the field of LiDAR-inertial odometry, many works have proposed using surfel maps instead of point clouds, as surfels fitted from a large number of points provide more accurate plane estimations. These approaches typically segment the point cloud into voxels and fit planes to the points within these voxels. However, fixed-grid voxels struggle to adapt to the irregular distributions in point clouds, often resulting in improper segmentation and reduced plane estimation accuracy. To address this issue, we propose in this paper a distribution-adaptive surfel map (DASM). DASM adaptively generates uniformly distributed sampling points on object surfaces from on each scan to extract the surfels, minimizing the risk of improper segmentation. Additionally, these sampling points can be arranged compactly to capture finer-grain details. We assume a 3D Gaussian point distribution for the surfel extraction, and efficiently integrate newly added points through incremental updates. These sampling points are organized in an ordered manner using voxel hashing to enable fast map access. We designed a more efficient neighborhood search method to accelerate both mapping and map queries. Experiments on various open-source datasets show that our method achieves superior accuracy and computational efficiency compared to relevant baselines. 

## 
<div align="center">
    <img src="Tree reconstruction_00.png" width = 100% >
</div>
Surfel maps in a tree of the NCLT dataset, constructed using different methods. (a) shows the point cloud map; (b) is our distribution-adaptive surfel map constructed by DASM-LIO; (c) is the multi-resolution voxel-based surfel map constructed by VoxelMap. Note the better adaptation of our approach to this particular point cloud.  
<br>

<div align="center">
    <img src="Mapping Comparison_00.png" width = 100% >
</div>
Comparison of partial mapping results between DASM-LIO (top) and VoxelMap (bottom) on the NCLT and Newer College datasets. (a) and (e) show the reconstruction results of the parking lot, with (b), (f) providing close-up views of vehicle. (c), (g) depict a plaza surrounding buildings, with (d), (h) showing close-up views of the building walls.  
<br>

<div align="center">
    <img src="Trajectory Comparison_00.png" width = 100% >
</div>
Comparison of estimated trajectories for different methods on several sequences of the [BotanicGarden dataset] (https://github.com/robot-pesg/BotanicGarden). The blue window highlights the details at the start and end points of each sequence. DASM-LIO achieved the best tracking in all sequences.  
