# FROM-FLAT-TO-3D
This is a repository that uses monocular depth estimation to generate 3D point clouds of video frames. The individual point clouds are in the end merged to create an independent scene representation.


# 3D Reconstruction from Monocular Video

This project reconstructs 3D point clouds from a monocular RGB video. The input video for this experiment was captured using a **Nothing Phone 3a**. Camera intrinsics for the pinhole camera model were chosen based on the phone specifications.  

## Pipeline Overview

The processing pipeline consists of four main steps:

1. **Frame Extraction:** The video is split into individual frames for processing.  
2. **Depth Estimation & Point Cloud Generation:** Each frame is processed using a monocular depth estimation model to predict depth maps, which are converted into 3D point clouds.  
3. **Point Cloud Merging:** Individual frame point clouds are merged using ICP-based registration. For this experiment, the merging threshold was set at **0.4**.  
4. **Evaluation:** The reconstructed 3D scene is evaluated using reprojection error and other metrics.  

## Sample Outputs

Below are sample outputs from the pipeline:

| RGB Frame | Depth Map | Point Cloud View 1 | Point Cloud View 2 |
|-----------|-----------|------------------|------------------|
| ![RGB Frame](Images/frame0.jpg) | ![Depth Map](Images/frame_00000_depth.png) | ![Point Cloud 1](Images/pointcloud1.png) | ![Point Cloud 2](Images/Pointcloud2.png) |

**Figure:** Sample outputs from the reconstruction pipeline: (a) input RGB frame, (b) predicted depth map, and (c–d) two views of the reconstructed point cloud.  
