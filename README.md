# CS231A_project
CS231A final project

This project is mainly based on the original 3D Gaussian Splatting https://github.com/graphdeco-inria/gaussian-splatting and DepthRegularized project

The first part, Inverse Depth, uses the original 3D Gaussian Splatting repository for analysis.
 
The DepthRegularized repository is used as a starting point, but it is broken . So, I modified numerous files to include Depth-based supervision: Supervising the rendered
depth map directly using an L1 loss against predicted or ground truth depth.The modified files included in this project should fix the broken repository and has better implementation of depth based regularization in terms of weightage between photometric and depth loss. Also, uses D/A instead of just using Depth as in repository which was breaking the training process.

Use environment setup from original 3D Gaussian for this project
