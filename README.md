# Awesome Point Cloud Normal Estimation

A curated list of representative point cloud normal estimation methods, organized following the taxonomy (**Table 1**) of the survey:

> **A Survey of Point Cloud Normal Estimation: Methods, Taxonomy, and Benchmarking**
> Paper Authors: Weijia Wang, Shuai Tong, Jiaxin Liu, Yuan-Gen Wang, and Xiaochun Cao — *Computational Visual Media*

> GitHub Page Maintainer: Weijia Wang, Jiaxin Liu, Xiemou Li

> Paper information and taxonomy are extracted from the survey unless otherwise noted. Code is marked **TBD** until a release is confirmed.


## Contents

- [Conventional Methods](#conventional-methods)
  - [PCA-based Methods](#pca-based-methods)
  - [Surface-based Methods](#surface-based-methods)
  - [Voronoi-based Methods](#voronoi-based-methods)
  - [Integral Invariant-based Methods](#integral-invariant-based-methods)
  - [Other Conventional Methods](#other-conventional-methods)
- [Learning-based Methods](#learning-based-methods)
  - [Regression-based Methods](#regression-based-methods)
  - [Fitting-based Methods](#fitting-based-methods)
  - [Other Learning-based Methods](#other-learning-based-methods)
- [Datasets](#datasets)
- [Benchmarks / Evaluation](#benchmarks--evaluation)

## Conventional Methods

### PCA-based Methods

#### PCA (Hoppe et al., 1992)

- **Paper:** Surface Reconstruction from Unorganized Points
- **Venue:** SIGGRAPH '92
- **Category:** Conventional Methods → PCA-based Methods
- **Description:** Estimates the normal via principal component (covariance) analysis of a local point neighborhood, taking the eigenvector associated with the smallest eigenvalue as the estimated normal.
- **Code:** [GitHub](https://github.com/hhoppe/Mesh-processing-library)

### Surface-based Methods

*Pending — to be added: MLS (Math. Comput. '98), Jet (CAGD '05)*

### Voronoi-based Methods

*Pending — to be added: BDBs (FSTTCS '06)*

### Integral Invariant-based Methods

*Pending — to be added: Integral Invariants (SGP '06)*

### Other Conventional Methods

*Pending — to be added: RHT (CGF '12), EAR (TOG '13), Low Rank (TVCG '22)*

## Learning-based Methods

### Regression-based Methods

#### PCPNet (Guerrero et al., 2018)

- **Paper:** PCPNet: Learning Local Shape Properties from Raw Point Clouds
- **Venue:** CGF '18
- **Category:** Learning-based Methods → Regression-based Methods (Point-based)
- **Description:** A patch-based regression framework that predicts normals directly from raw point clouds, using a quaternion-based Spatial Transformer Network for rotation invariance and symmetric feature aggregation followed by an MLP.
- **Code:** [GitHub](https://github.com/paulguerrero/pcpnet)

#### Nesti-Net (Ben-Shabat et al., 2019)

- **Paper:** Nesti-Net: Normal Estimation for Unstructured 3D Point Clouds Using Convolutional Neural Networks
- **Venue:** CVPR '19
- **Category:** Learning-based Methods → Regression-based Methods (Multi-scale)
- **Description:** A multi-scale regression method that uses multi-scale point statistics and a mixture-of-experts architecture to select the optimal patch scale per point before estimating normals.
- **Code:** [GitHub](https://github.com/sitzikbs/Nesti-Net)

#### NeAF (Li et al., 2023)

- **Paper:** NeAF: Learning Neural Angle Fields for Point Normal Estimation
- **Venue:** AAAI '23
- **Category:** Learning-based Methods → Regression-based Methods (Coarse-to-fine)
- **Description:** Learns neural angle fields (NeAFs) by predicting angle offsets between sampled query normals and ground-truth normals.
- **Code:** [GitHub](https://github.com/lisj575/NeAF)

### Fitting-based Methods

#### DeepFit (Ben-Shabat & Gould, 2020)

- **Paper:** DeepFit: 3D Surface Fitting via Neural Network Weighted Least Squares
- **Venue:** ECCV '20
- **Category:** Learning-based Methods → Fitting-based Methods (Explicit Surface Fit.)
- **Description:** An explicit surface fitting method in which a PointNet-based encoder predicts per-point weights for polynomial (n-jet) surface approximation, capturing curvature variation more effectively than planar fitting.
- **Code:** [GitHub](https://github.com/sitzikbs/DeepFit)

### Other Learning-based Methods

*Pending — to be added: Refine-Net (TPAMI '23, Hybrid); NGLO (SIGGRAPH Asia '23), NeuralGF (NeurIPS '23), CAP-UDF (TPAMI '24, Gradient-based)*

## Datasets

*To be added.*

## Benchmarks / Evaluation

*To be added.*
