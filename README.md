# RIU-Net for point cloud semantic segmentaion
- This work represents the implementation of the [RIU-Net: Embarrassingly simple semantic segmentation of 3D LiDAR point cloud](https://arxiv.org/pdf/1905.08748.pdf) paper with the [SemanticKITTI](http://semantic-kitti.org/dataset.html) dataset related to semantic segmentation of point clouds made for autonomous cars.
- Paper data for this implementation (can change depending on the context of work):
  - Loss function: CrossEntropyLoss
  - Batch size: 8
  - Epochs: 10
  - Learning rate: 0.001
  - Batch normalization with momentum = 0.99
  - Optimizer: Adam or SGD
- Current status: Getting there
## **Important considerations**:
  - Using pytorch functions.
  - The network trains with 2D images of point clouds, which means that some pre-processing of the dataset was done, such as:
    - Spherical projection of the `.bin` and `.label` archives.
    - Split the pojections into two kinds of image values: `Reflectance` and `depth` (2 channels image), and `label` index (1 channel image).
    - The `label` dictionary can be found at the [semantic kitti api](https://github.com/PRBonn/semantic-kitti-api) repository and the `learning_map` dictionary is the one used in this work.
    - Image dimensions set to 64x1024 to match the dataset.
    - Since this work is done using Google Colab notebooks, the dataset was uploaded on google drive beforehand.
  - All the pre-processing and visualization was done using the [Cloud2DImageConverter](https://github.com/alunos-pfc/Cloud2DImageConverter) repository
  - Any other information about this work can be found on the notebooks text cells as well as the visualization tutorial.
