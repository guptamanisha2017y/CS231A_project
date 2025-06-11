# CS231A_project
CS231A final project

This project is mainly based on the original 3D Gaussian Splatting https://github.com/graphdeco-inria/gaussian-splatting and DepthRegularized project

The first part, Inverse Depth, uses the original 3D Gaussian Splatting repository for analysis.
 
The DepthRegularized repository was used as a starting point, but it was broken and had an incorrect implementation of depth-based supervision loss. So, I modified the code base to include Depth-based supervision: 

Data Preparation:
COLMAP GUI can be used to create sparse point clouds and Camera matrices.

## Training
For training, use:
## Example: 
##    <datadir> = ./data/nerf_llff_fewshot_resize/fern
##    <outdir>  = ./output/baseline
## For our DepthRegularization (method2), add --depth and --usedepthReg arguments
python train.py -s <datadir> --eval --port 6312 --model_path <outdir>/method2 --resolution 1 --kshot 5 --seed 3 --depth --usedepthReg

File Name: backward. cu
- Implementing depth supervision based upon D/A, which weights depth along the ray
File Name: train.py
- Implementation of depth-based regularization in terms of weightage between photometric and depth loss.
- Supervising the rendered depth map directly using an L1 loss against predicted or ground truth depth.
- Preparing the proper data structure to initialize Gaussians for training and rendering

