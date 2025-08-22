# Learning High-Resolution 3D Spine Mesh Reconstruction from Clinical Anisotropic MRI through Differentiable Rendering

**Authors:** Sai Natarajan, Ludovic Humbert, Miguel A. González Ballester

## News
- **[2025]** Code will be made available soon
- **[2024]** Preliminary work presented at MICCAI 2024

## Abstract

We present a novel methodology to address the crucial challenge of leveraging sparse annotations to perform high-resolution 3D shape reconstructions from medical images. Our approach utilizes a differentiable rendering based inverse-graphics framework to perform 3D anatomical shape reconstruction without complete 3D supervision. Our pipeline involves our shape reconstruction network (MRI2Mesh) to reconstruct 3D meshes from medical images and a differentiable renderer to produce renderings of the shapes in the form of silhouettes and depth maps. This analysis-by-synthesis approach bridges the gap between 3D reconstruction and downstream tasks such as finite element modeling and biomechanical simulations.

## Key Contributions

- **First application** of differentiable rendering for 3D shape reconstruction in medical imaging
- **Novel sparse annotation approach** reconstructing high-resolution 3D meshes from 2D supervision through analysis-by-synthesis
- **Joint optimization** of 3D shape reconstruction network and differentiable renderer
- **Comprehensive evaluation** on vertebrae and intervertebral disc reconstruction from multi-view rendering

## Method Overview

![Method Overview](assets/method_overview.png)

Our approach follows a **Volume → Mesh → Render → Optimize** paradigm:

1. **MRI2Mesh Network**: Reconstructs 3D triangle meshes directly from clinical MRI volumes
2. **Differentiable Renderer**: Generates 2D silhouette and depth renderings from predicted meshes
3. **2D Supervision**: Computes loss between rendered outputs and ground truth 2D renderings instead of expensive 3D mesh supervision
4. **Joint Optimization**: End-to-end training using hybrid rendering loss (silhouette + depth + geometric regularization)

### Architecture Components

- **Image Encoder**: 3D-ResNet50 for patient-specific feature extraction
- **Mesh Deformation**: Graph Convolutional Networks (GCNs) with cross-level feature fusion
- **Differentiable Renderer**: PyTorch3D implementation with soft rasterization
- **Loss Functions**: Dice loss (silhouette) + L1 loss (depth) + Laplacian smoothing + normal consistency

## Code Availability

**The complete implementation will be made available soon!**

## Citation

If you find this work useful, please consider citing our paper (citation details will be updated upon publication).

## Contact

For questions about this work, please contact the authors.

## License

This project will be released under the MIT License.
