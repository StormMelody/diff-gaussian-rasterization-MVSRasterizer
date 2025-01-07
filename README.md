Our work is based on the code provided by “3D Gaussian Splatting for Real-Time Radiance Field Rendering”, which is available at https://github.com/graphdeco-inria/gaussian-splatting. We can finally be able to rasterize 3D Gaussians from different views simultaneously, instead of using loops.

Specifically, we only changed the Python and CUDA codes in gaussian_renderer and submodules/diff-gaussian-rasterization, so that Gaussian Splatting can simultaneously calculate rasterization and rendering from multiple perspectives, and back-propagate to update the parameters of 3D Gaussians for multiple perspectives at the same time.

Most of our modifications are made to the rasterization engine of "3D Gaussian Splatting for Real-Time Rendering of Radiance Fields", mainly modifying .h and .cu files, including almost all serial and parallel parts.

If you need to use this code, just refer to gaussian_render and modify the Python code to input images from multiple perspectives and corresponding camera parameters.

Then, install it using the following command:
```bash
pip install submodules/diff-gaussian-rasterization
```