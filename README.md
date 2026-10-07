# Awesome Point Cloud Normal Estimation

**English** | [简体中文](README.zh-CN-third-caogao2-version.md)

A list of representative point cloud normal estimation methods outlined in the survey:

> **A Survey of Point Cloud Normal Estimation: Methods, Taxonomy, and Benchmarking**
> Weijia Wang, Shuai Tong, Jiaxin Liu, Yuan-Gen Wang, and Xiaochun Cao - *Computational Visual Media*

For any inquiries or suggestions, please contact the repository maintainers: 
* Weijia Wang (wwj@gzhu.edu.cn)
* Jiaxin Liu (jiaxinliu@e.gzhu.edu.cn)
* Xiemou Li (lixiemou@e.gzhu.edu.cn)

## Table of Contents
------
- [Awesome Point Cloud Normal Estimation](#awesome-point-cloud-normal-estimation)
  - [Table of Contents](#table-of-contents)
  - [Conventional Methods](#conventional-methods)
    - [PCA-based Methods](#pca-based-methods)
      - [Basic Plane Fitting](#basic-plane-fitting)
      - [Neighborhood Refinement-based PCA](#neighborhood-refinement-based-pca)
      - [Sub-neighborhood Clustering-based PCA](#sub-neighborhood-clustering-based-pca)
      - [Statistical and Voting-based PCA](#statistical-and-voting-based-pca)
    - [Surface-based Methods](#surface-based-methods)
      - [Explicit Surface Modeling](#explicit-surface-modeling)
      - [Implicit Surface Modeling](#implicit-surface-modeling)
    - [Voronoi-based Methods](#voronoi-based-methods)
    - [Integral Invariant-based Methods](#integral-invariant-based-methods)
    - [Other Conventional Methods](#other-conventional-methods)
  - [Learning-based Methods](#learning-based-methods)
    - [Regression-based Methods](#regression-based-methods)
      - [CNN-based Regression](#cnn-based-regression)
      - [Point-based Regression](#point-based-regression)
      - [Multi-scale Regression](#multi-scale-regression)
      - [Attention-driven Regression](#attention-driven-regression)
      - [Coarse-to-fine Pipelines](#coarse-to-fine-pipelines)
      - [Joint Denoising and Normal Estimation](#joint-denoising-and-normal-estimation)
    - [Fitting-based Methods](#fitting-based-methods)
      - [Neural Plane Fitting](#neural-plane-fitting)
      - [Neural Explicit Surface Fitting](#neural-explicit-surface-fitting)
      - [Neural Implicit Surface Fitting](#neural-implicit-surface-fitting)
    - [Other Learning-based Methods](#other-learning-based-methods)
      - [Hybrid](#hybrid)
      - [Gradient-based](#gradient-based)
  - [Normal Orientation](#normal-orientation)
  - [Datasets](#datasets)
    - [Synthetic Datasets](#synthetic-datasets)
    - [Real-world and Mixed Datasets](#real-world-and-mixed-datasets)
  - [Benchmarks and Evaluation](#benchmarks-and-evaluation)
    - [Metrics](#metrics)
    - [Evaluation Protocols](#evaluation-protocols)
  - [Applications](#applications)
    - [Denoising](#denoising)
    - [Surface Reconstruction](#surface-reconstruction)
    - [Registration](#registration)
  - [Future Directions](#future-directions)
  - [Related Resources](#related-resources)


## Conventional Methods
-----
### PCA-based Methods

#### Basic Plane Fitting

- **PCA** (Hoppe et al.) - *Surface Reconstruction from Unorganized Points*. SIGGRAPH 1992. [Paper](https://doi.org/10.1145/142920.134011)
- **Pauly et al.** - *Efficient Simplification of Point-Sampled Surfaces*. IEEE VIS 2002. [Paper](https://doi.org/10.1109/VISUAL.2002.1183771)
- **Mitra and Nguyen** - *Estimating Surface Normals in Noisy Point Cloud Data*. Symposium on Computational Geometry 2003. [Paper](https://doi.org/10.1145/777792.777840)
- **Anisotropic** (Lange and Polthier) - *Anisotropic Smoothing of Point Sets*. CAGD 2005. [Paper](https://doi.org/10.1016/j.cagd.2005.06.010)

#### Neighborhood Refinement-based PCA

- **WLOP** (Huang et al.) - *Consolidation of Unorganized Point Clouds for Surface Reconstruction*. TOG 2009. [Paper](https://doi.org/10.1145/1618452.1618515)
- **DetMM** (Khaloo and Lattanzi) - *Robust Normal Estimation and Region Growing Segmentation of Infrastructure 3D Point Cloud Models*. Advanced Engineering Informatics 2017. [Paper](https://doi.org/10.1016/j.aei.2017.07.002)
- **Meng et al.** - *An Investigation of the High Efficiency Estimation Approach of the Large-Scale Scattered Point Cloud Normal Vector*. Applied Sciences 2018. [Paper](https://doi.org/10.3390/app8030454)
- **Wang et al.** - *Indoor Point Cloud Segmentation Using a Modified Region Growing Algorithm and Accurate Normal Estimation*. IEEE Access 2023. [Paper](https://doi.org/10.1109/ACCESS.2023.3270709)

#### Sub-neighborhood Clustering-based PCA

- **Zhang et al.** - *Point Cloud Normal Estimation via Low-Rank Subspace Clustering*. Computers & Graphics 2013. [Paper](https://doi.org/10.1016/j.cag.2013.05.008)
- **Hao et al.** - *Normal Estimation of Point Cloud Based on Sub-neighborhood Clustering*. Measurement Science and Technology 2018. [Paper](https://doi.org/10.1088/1361-6501/aadf12)
- **Cao et al.** - *Normal Estimation via Shifted Neighborhood for Point Cloud*. Journal of Computational and Applied Mathematics 2018. [Paper](https://doi.org/10.1016/j.cam.2017.04.027)
- **Yu et al.** - *Robust Point Cloud Normal Estimation via Neighborhood Reconstruction*. Advances in Mechanical Engineering 2019. [Paper](https://doi.org/10.1177/1687814019836043)
- **Zhang et al.** - *Point Cloud Normal Estimation by Fast Guided Least Squares Representation*. IEEE Access 2020. [Paper](https://doi.org/10.1109/ACCESS.2020.2998468)
- **Zhao et al.** - *Robust Normal Estimation for 3D LiDAR Point Clouds in Urban Environments*. Sensors 2019. [Paper](https://doi.org/10.3390/s19051248)

#### Statistical and Voting-based PCA

- **Mura et al.** - *Robust Normal Estimation in Unstructured 3D Point Clouds by Selective Normal Space Exploration*. The Visual Computer 2018. [Paper](https://doi.org/10.1007/s00371-018-1542-6)
- **PCV** (Zhang et al.) - *Multi-Normal Estimation via Pair Consistency Voting*. TVCG 2019. [Paper](https://doi.org/10.1109/TVCG.2018.2827998)

### Surface-based Methods

#### Explicit Surface Modeling

- **Jet** (Cazals and Pouget) - *Estimating Differential Quantities Using Polynomial Fitting of Osculating Jets*. CAGD 2005. [Paper](https://doi.org/10.1016/j.cagd.2004.09.004)
- **Algebraic Sphere Fitting** (Guennebaud and Gross) - *Algebraic Point Set Surfaces*. TOG 2007. [Paper](https://doi.org/10.1145/1276377.1276406)
- **Octree-based Multiscale Sphere Fitting** (Zhao et al.) - *3-D Point Cloud Normal Estimation Based on Fitting Algebraic Spheres*. ICIP 2016. [Paper](https://doi.org/10.1109/ICIP.2016.7532827)
- **Curvature-aware Algebraic Sphere Fitting** (Wang et al.) - *Consistent Orientation Normal Vector Estimation for Scattered Point Cloud*. Computers & Graphics 2026. [Paper](https://doi.org/10.1016/j.cag.2026.104534)

#### Implicit Surface Modeling

- **MLS** (Levin) - *The Approximation Power of Moving Least-Squares*. Mathematics of Computation 1998. [Paper](https://doi.org/10.1090/S0025-5718-98-00974-0)
- **Point Set Surfaces** (Alexa et al.) - *Point Set Surfaces*. IEEE VIS 2001. [Paper](https://doi.org/10.1109/VISUAL.2001.964489)
- **Point Set Surfaces** (Alexa et al.) - *Computing and Rendering Point Set Surfaces*. TVCG 2003. [Paper](https://doi.org/10.1109/TVCG.2003.1175093)
- **Adaptive MLS** (Dey and Sun) - *An Adaptive MLS Surface for Reconstruction with Guarantees*. SGP 2005. [Paper](https://doi.org/10.2312/SGP/SGP05/043-052)

### Voronoi-based Methods

- **Voronoi Filtering** (Amenta and Bern) - *Surface Reconstruction by Voronoi Filtering*. Symposium on Computational Geometry 1998. [Paper](https://doi.org/10.1145/276884.276889)
- **Dey et al.** - *Normal Estimation for Point Clouds: A Comparison Study for a Voronoi Based Method*. PBG 2005. [Paper](https://doi.org/10.1109/PBG.2005.194062)
- **BDBs** (Dey and Sun) - *Normal and Feature Approximations from Noisy Point Clouds*. FSTTCS 2006. [Paper](https://doi.org/10.1007/11944836_5)
- **Dey and Goswami** - *Provable Surface Reconstruction from Noisy Samples*. Computational Geometry 2006. [Paper](https://doi.org/10.1016/j.comgeo.2005.10.006)
- **Alliez et al.** - *Voronoi-Based Variational Reconstruction of Unoriented Point Sets*. SGP 2007. [Paper](https://doi.org/10.2312/SGP/SGP07/039-048)
- **Merigot et al.** - *Voronoi-Based Curvature and Feature Estimation from Point Clouds*. TVCG 2011. [Paper](https://doi.org/10.1109/TVCG.2010.261)

### Integral Invariant-based Methods

- **Integral Invariants** (Yang et al.) - *Robust Principal Curvatures on Multiple Scales*. SGP 2006. [Paper](https://doi.org/10.2312/SGP/SGP06/223-226)
- **Pottmann et al.** - *Principal Curvatures from the Integral Invariant Viewpoint*. CAGD 2007. [Paper](https://doi.org/10.1016/j.cagd.2007.07.004)
- **Pottmann et al.** - *Integral Invariants for Robust Geometry Processing*. CAGD 2009. [Paper](https://doi.org/10.1016/j.cagd.2008.01.002)
- **Lai et al.** - *Robust Principal Curvatures Using Feature Adapted Integral Invariants*. SIAM/ACM Joint Conference on Geometric and Physical Modeling 2009. [Paper](https://doi.org/10.1145/1629255.1629298)
- **Lachaud et al.** - *Robust and Convergent Curvature and Normal Estimators with Digital Integral Invariants*. Modern Approaches to Discrete Curvature 2017. [Paper](https://doi.org/10.1007/978-3-319-58002-9_9)

### Other Conventional Methods

- **Statistical Ensembles** (Yoon et al.) - *Surface and Normal Ensembles for Surface Reconstruction*. CAD 2007. [Paper](https://doi.org/10.1016/j.cad.2007.02.008)
- **RHT** (Boulch and Marlet) - *Fast and Robust Normal Estimation for Point Clouds with Sharp Features*. CGF 2012. [Paper](https://doi.org/10.1111/j.1467-8659.2012.03181.x)
- **EAR** (Huang et al.) - *Edge-Aware Point Set Resampling*. TOG 2013. [Paper](https://doi.org/10.1145/2421636.2421645)
- **Low Rank** (Lu et al.) - *Low Rank Matrix Approximation for 3D Geometry Filtering*. TVCG 2022. [Paper](https://doi.org/10.1109/TVCG.2020.3026785)
- **Depth-Buffer-based LiDAR Model** (Kirchengast and Watzenig) - *A Depth-Buffer-Based Lidar Model With Surface Normal Estimation*. IEEE TITS 2024. [Paper](https://doi.org/10.1109/TITS.2024.3371531)

## Learning-based Methods
-----
### Regression-based Methods

#### CNN-based Regression

- **HoughCNN** (Boulch and Marlet) - *Deep Learning for Robust Normal Estimation in Unstructured Point Clouds*. CGF 2016. [Paper](https://doi.org/10.1111/cgf.12983) / [Code](https://github.com/aboulch/normals_HoughCNN)
- **ToFNet** (Molnar et al.) - *ToFNet: Efficient Normal Estimation for Time-of-Flight Depth Cameras*. ICCVW 2021. [Paper](https://doi.org/10.1109/ICCVW54120.2021.00205) / [Code](https://github.com/molnarszilard/ToFNest)
- **GeoDualCNN** (Wei et al.) - *GeoDualCNN: Geometry-Supporting Dual Convolutional Neural Network for Noisy Point Clouds*. TVCG 2023. [Paper](https://doi.org/10.1109/TVCG.2021.3113463)
- **Yi et al.** - *Point Cloud Normal Estimation via Representation Learning on Height Maps*. ACM MM Asia 2024. [Paper](https://doi.org/10.1145/3696409.3700185)
- **Norest-Net** (Zhang et al.) - *Norest-Net: Normal Estimation Neural Network for 3-D Noisy Point Clouds*. TNNLS 2025. [Paper](https://doi.org/10.1109/TNNLS.2024.3352974)

#### Point-based Regression

- **PointNet** (Qi et al.) - *PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation*. CVPR 2017. [Paper](https://doi.org/10.1109/CVPR.2017.16)
- **PointNet++** (Qi et al.) - *PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space*. NeurIPS 2017. [Paper](https://papers.nips.cc/paper/2017/hash/d8bf84be3800d12f74d8b05e9b89836f-Abstract.html)+++++
- **PCPNet** (Guerrero et al.) - *PCPNet: Learning Local Shape Properties from Raw Point Clouds*. CGF 2018. [Paper](https://doi.org/10.1111/cgf.13343) / [Code](https://github.com/paulguerrero/pcpnet)
- **DensePoint** (Liu et al.) - *DensePoint: Learning Densely Contextual Representation for Efficient Point Cloud Processing*. ICCV 2019. [Paper](https://doi.org/10.1109/ICCV.2019.00534) / [Code](https://github.com/Yochengliu/DensePoint)
- **Pistilli et al.** - *Point Cloud Normal Estimation with Graph-Convolutional Neural Networks*. ICMEW 2020. [Paper](https://doi.org/10.1109/ICMEW46912.2020.9105972) / [Code](https://github.com/FilippoPistilli/Point-Cloud-Normal-Estimation)
- **Wang et al.** - *Deep Point Cloud Normal Estimation via Triplet Learning*. ICME 2022. [Paper](https://doi.org/10.1109/ICME52920.2022.9859844)
- **ConW-Net** (Wang et al.) - *Weighted Point Cloud Normal Estimation*. ICME 2023. [Paper](https://doi.org/10.1109/ICME55011.2023.00345) / [Code](https://github.com/weijiawang96/ConW-Net)
- **VecKM** (Yuan et al.) - *A Linear Time and Space Local Point Cloud Geometry Encoder via Vectorized Kernel Mixture*. ICML 2024. [Paper](https://dl.acm.org/doi/10.5555/3692070.3694457)

#### Multi-scale Regression

- **PCPNet-ms** (Guerrero et al.) - *PCPNet: Learning Local Shape Properties from Raw Point Clouds*. CGF 2018. [Paper](https://doi.org/10.1111/cgf.13343) / [Code](https://github.com/paulguerrero/pcpnet)
- **Nesti-Net** (Ben-Shabat et al.) - *Nesti-Net: Normal Estimation for Unstructured 3D Point Clouds Using Convolutional Neural Networks*. CVPR 2019. [Paper](https://doi.org/10.1109/CVPR.2019.01035) / [Code](https://github.com/sitzikbs/Nesti-Net)
- **NormNet** (Hyeon et al.) - *NormNet: Point-Wise Normal Estimation Network for Three-Dimensional Point Cloud Data*. International Journal of Advanced Robotic Systems 2019. [Paper](https://doi.org/10.1177/1729881419857532)
- **Hashimoto and Saito** - *Normal Estimation for Accurate 3D Mesh Reconstruction with Point Cloud Model Incorporating Spatial Structure*. CVPRW 2019. [Paper](https://openaccess.thecvf.com/content_CVPRW_2019/html/Deep_Vision_Workshop/Hashimoto_Normal_Estimation_for_Accurate_3D_Mesh_Reconstruction_with_Point_Cloud_CVPRW_2019_paper.html)+++++
- **LPFC** (Zhou et al.) - *Normal Estimation for 3D Point Clouds via Local Plane Constraint and Multi-Scale Selection*. CAD 2020. [Paper](https://doi.org/10.1016/j.cad.2020.102916)
- **MSECNet** (Xiu et al.) - *MSECNet: Accurate and Robust Normal Estimation for 3D Point Clouds by Multi-Scale Edge Conditioning*. ACM MM 2023. [Paper](https://doi.org/10.1145/3581783.3613762) / [Code](https://github.com/martianxiu/MSECNet)
- **CMG-Net** (Wu et al.) - *CMG-Net: Robust Normal Estimation for Point Clouds via Chamfer Normal Distance and Multi-Scale Geometry*. AAAI 2024. [Paper](https://doi.org/10.1609/aaai.v38i6.28434)
- **FAHNet** (Wang et al.) - *FAHNet: Accurate and Robust Normal Estimation for Point Clouds via Frequency-Aware Hierarchical Geometry*. CGF 2025. [Paper](https://doi.org/10.1111/cgf.70264)

#### Attention-driven Regression

- **NINormal** (Wang and Prisacariu) - *Neighbourhood-Insensitive Point Cloud Normal Estimation Network*. BMVC 2020. [Paper](https://ora.ox.ac.uk/objects/uuid:317bceec-63f6-46b0-af15-e222206fe61e) / [Code](https://github.com/ActiveVisionLab/NINormal)+++++
- **PCT** (Guo et al.) - *PCT: Point Cloud Transformer*. Computational Visual Media 2021. [Paper](https://doi.org/10.1007/s41095-021-0229-5)
- **Xiang et al.** - *Walk in the Cloud: Learning Curves for Point Clouds Shape Analysis*. ICCV 2021. [Paper](https://doi.org/10.1109/ICCV48922.2021.00095)
- **Patch Stitching** (Zhou et al.) - *Fast and Accurate Normal Estimation for Point Clouds via Patch Stitching*. CAD 2022. [Paper](https://doi.org/10.1016/j.cad.2021.103121)
- **Zhou et al.** - *Robust Point Cloud Normal Estimation via Multi-Level Critical Point Aggregation*. The Visual Computer 2024. [Paper](https://doi.org/10.1007/s00371-024-03532-x)
- **HGT** (Lin et al.) - *Normal Transformer: Extracting Surface Geometry From LiDAR Points Enhanced by Visual Semantics*. IEEE TIV 2024. [Paper](https://doi.org/10.1109/TIV.2024.3355774)
- **GAM-Net** (Jin et al.) - *Enhanced Normal Estimation of Point Clouds via Fine-Grained Geometric Information Learning*. MVA 2025. [Paper](https://doi.org/10.1007/s00138-025-01671-2)
- **LiSu** (Malic et al.) - *LiSu: A Dataset and Method for LiDAR Surface Normal Estimation*. CVPR 2025. [Paper](https://doi.org/10.1109/CVPR52734.2025.01588) / [Code](https://github.com/malicd/LiSu)111111

#### Coarse-to-fine Pipelines

- **NH-Net** (Zhou et al.) - *Geometry and Learning Co-Supported Normal Estimation for Unstructured Point Cloud*. CVPR 2020. [Paper](https://doi.org/10.1109/CVPR42600.2020.01325) / [Code](https://github.com/hrzhou2/NH-Net-master)
- **NeAF** (Li et al.) - *NeAF: Learning Neural Angle Fields for Point Normal Estimation*. AAAI 2023. [Paper](https://doi.org/10.1609/aaai.v37i1.25224) / [Code](https://github.com/lisj575/NeAF)
- **HAE-Net** (Li et al.) - *High-Quality Point Cloud Oriented Normal Estimation via Hybrid Angular and Euclidean Distance Encoding*. CVPR 2025. [Paper](https://doi.org/10.1109/CVPR52734.2025.00128)
#### Joint Denoising and Normal Estimation

- **Lu et al.** - *Deep Feature-Preserving Normal Estimation for Point Cloud Filtering*. CAD 2020. [Paper](https://doi.org/10.1016/j.cad.2020.102860)
- **Contrastive Learning** (De Silva Edirimuni et al.) - *Contrastive Learning for Joint Normal Estimation and Point Cloud Filtering*. TVCG 2023. [Paper](https://doi.org/10.1109/TVCG.2023.3263866)
- **GeoDualCNN** (Wei et al.) - *GeoDualCNN: Geometry-Supporting Dual Convolutional Neural Network for Noisy Point Clouds*. TVCG 2023. [Paper](https://doi.org/10.1109/TVCG.2021.3113463)
- **PCDNF** (Liu et al.) - *PCDNF: Revisiting Learning-Based Point Cloud Denoising via Joint Normal Filtering*. TVCG 2024. [Paper](https://doi.org/10.1109/TVCG.2023.3292464) / [Code](https://github.com/LabZhengLiu/PCDNF)
- **PN-Internet** (Yi et al.) - *PN-Internet: Point-and-Normal Interactive Network for Noisy Point Clouds*. IEEE TGRS 2024. [Paper](https://doi.org/10.1109/TGRS.2024.3395785)

### Fitting-based Methods

#### Neural Plane Fitting

- **IterNet** (Lenssen et al.) - *Deep Iterative Surface Normal Estimation*. CVPR 2020. [Paper](https://doi.org/10.1109/CVPR42600.2020.01126)
- **TRNet / MTRNet** (Cao et al.) - *Latent Tangent Space Representation for Normal Estimation*. TIE 2022. [Paper](https://doi.org/10.1109/TIE.2021.3053904)
- **Geometry-guided** (Zhang et al.) - *Geometry Guided Deep Surface Normal Estimation*. CAD 2022. [Paper](https://doi.org/10.1016/j.cad.2021.103119)
- **Zhou et al.** - *Improvement of Normal Estimation for Point Clouds via Simplifying Surface Fitting*. CAD 2023. [Paper](https://doi.org/10.1016/j.cad.2023.103533)333333

#### Neural Explicit Surface Fitting

- **DeepFit** (Ben-Shabat and Gould) - *DeepFit: 3D Surface Fitting via Neural Network Weighted Least Squares*. ECCV 2020. [Paper](https://doi.org/10.1007/978-3-030-58452-8_2) / [Code](https://github.com/sitzikbs/DeepFit)
- **AdaFit** (Zhu et al.) - *AdaFit: Rethinking Learning-Based Normal Estimation on Point Clouds*. ICCV 2021. [Paper](https://doi.org/10.1109/ICCV48922.2021.00606) / [Code](https://github.com/Runsong123/AdaFit)
- **GraphFit** (Li et al.) - *GraphFit: Learning Multi-Scale Graph-Convolutional Representation for Point Cloud Normal Estimation*. ECCV 2022. [Paper](https://doi.org/10.1007/978-3-031-19824-3_38) / [Code](https://github.com/UestcJay/GraphFit)
- **ZTEE** (Du et al.) - *Rethinking the Approximation Error in 3D Surface Fitting for Point Cloud Normal Estimation*. CVPR 2023. [Paper](https://doi.org/10.1109/CVPR52729.2023.00915)
- **Jin et al.** - *Asymmetrical Siamese Network for Point Clouds Normal Estimation*. Expert Systems with Applications 2025. [Paper](https://doi.org/10.1016/j.eswa.2025.127401)333333
- **OscuFit** (Fu et al.) - *OscuFit: Learning to Fit Osculating Implicit Quadrics for Point Clouds*. AAAI 2026. [Paper](https://doi.org/10.1609/aaai.v40i5.37405)

#### Neural Implicit Surface Fitting

- **HSurf-Net** (Li et al.) - *HSurf-Net: Normal Estimation for 3D Point Clouds by Learning Hyper Surfaces*. NeurIPS 2022. [Paper](https://dl.acm.org/doi/10.5555/3600270.3600575) / [Code](https://github.com/LeoQLi/HSurf-Net)
- **SHS-Net** (Li et al.) - *SHS-Net: Learning Signed Hyper Surfaces for Oriented Normal Estimation of Point Clouds*. CVPR 2023. [Paper](https://doi.org/10.1109/CVPR52729.2023.01306) / [Code](https://github.com/LeoQLi/SHS-Net)
- **SHS-Net** (Li et al.) - *Learning Signed Hyper Surfaces for Oriented Point Cloud Normal Estimation*. TPAMI 2024. [Paper](https://doi.org/10.1109/TPAMI.2024.3431221) / [Code](https://github.com/LeoQLi/SHS-Net)

### Other Learning-based Methods

#### Hybrid

- **PointProNets** (Roveri et al.) - *PointProNets: Consolidation of Point Clouds with Convolutional Neural Networks*. CGF 2018. [Paper](https://doi.org/10.1111/cgf.13344)
- **Zhang et al.** - *Mixed Normal Vector Estimation Strategy for Unstructured Point Clouds*. CCDC 2020. [Paper](https://doi.org/10.1109/CCDC49329.2020.9164799)
- **Refine-Net** (Zhou et al.) - *Refine-Net: Normal Refinement Neural Network for Noisy Point Clouds*. TPAMI 2023. [Paper](https://doi.org/10.1109/TPAMI.2022.3145877) / [Code](https://github.com/hrzhou2/refinenet)
- **PFF-Net** (Li et al.) - *PFF-Net: Patch Feature Fitting for Point Cloud Normal Estimation*. TVCG 2026. [Paper](https://doi.org/10.1109/TVCG.2025.3638450)

#### Gradient-based

- **NGLO** (Li et al.) - *Neural Gradient Learning and Optimization for Oriented Point Normal Estimation*. SIGGRAPH Asia 2023. [Paper](https://doi.org/10.1145/3610548.3618253) / [Code](https://github.com/LeoQLi/NGLO)
- **NeuralGF** (Li et al.) - *NeuralGF: Unsupervised Point Normal Estimation by Learning Neural Gradient Function*. NeurIPS 2023. [Paper](https://dl.acm.org/doi/abs/10.5555/3666122.3669004) / [Code](https://github.com/LeoQLi/NeuralGF)
- **LevelSetUDF** (Zhou et al.) - *Learning a More Continuous Zero Level Set in Unsigned Distance Fields through Level Set Projection*. ICCV 2023. [Paper](https://doi.org/10.1109/ICCV51070.2023.00295) / [Code](https://github.com/junshengzhou/LevelSetUDF)
- **CAP-UDF** (Zhou et al.) - *CAP-UDF: Learning Unsigned Distance Functions Progressively from Raw Point Clouds with Consistency-Aware Field Optimization*. TPAMI 2024. [Paper](https://doi.org/10.1109/TPAMI.2024.3392364) / [Code](https://github.com/junshengzhou/CAP-UDF)
- **LGSF** (Li et al.) - *Learning Normals of Noisy Points by Local Gradient-Aware Surface Filtering*. ICCV 2025. [Paper](https://doi.org/10.1109/ICCV51701.2025.02677) / [Code](https://github.com/LeoQLi/LGSF)

## Normal Orientation
-----

- **MST** (Hoppe et al.) - *Surface Reconstruction from Unorganized Points*. SIGGRAPH 1992. [Paper](https://doi.org/10.1145/142920.134011)
- **Mullen et al.** - *Signing the Unsigned: Robust Surface Reconstruction from Raw Pointsets*. CGF 2010. [Paper](https://doi.org/10.1111/j.1467-8659.2010.01782.x)
- **GWN** (Liu et al.) - *Consistent Point Orientation for Manifold Surfaces via Boundary Integration*. SIGGRAPH 2024. [Paper](https://doi.org/10.1145/3641519.3657475)
- **WNNC** (Lin et al.) - *Fast and Globally Consistent Normal Orientation based on the Winding Number Normal Consistency*. TOG 2024. [Paper](https://doi.org/10.1145/3687895)
- **QPBO** (Hoppe et al.) - *Surface Reconstruction from Unorganized Points*. SIGGRAPH 1992. [Paper](https://doi.org/10.1145/142920.134011)222222
- **ODP** (Hoppe et al.) - *Surface Reconstruction from Unorganized Points*. SIGGRAPH 1992. [Paper](https://doi.org/10.1145/142920.134011)222222

## Datasets
-----
### Synthetic Datasets

- **ModelNet40** (2015) - Synthetic mesh benchmark commonly used in point cloud learning. [Dataset](https://modelnet.cs.princeton.edu/)
- **PCPNet Dataset** (2018) - CAD-like and non-CAD-like shapes with controlled noise and sampling density. [Dataset](https://github.com/paulguerrero/pcpnet)
- **ABC Dataset** (2019) - Large-scale CAD model collection for geometric deep learning. [Dataset](https://deep-geometry.github.io/abc-dataset/)
- **FamousShape** (2023) - Iconic shapes with varied noise levels and sampling densities. [Dataset](https://github.com/LeoQLi/SHS-Net)
- **Multi-view** (2025) - Multi-view synthetic scans for normal estimation. [Paper](https://doi.org/10.1016/j.eswa.2025.127401)
- **LiSu** (2025) - Large-scale synthetic LiDAR data for autonomous driving scenarios. [Dataset](https://github.com/malicd/LiSu)
- **HAE Virtual-scan** (2025) - Virtual-scan data for oriented normal estimation. [Paper](https://openaccess.thecvf.com/content/CVPR2025/html/Li_High-quality_Point_Cloud_Oriented_Normal_Estimation_via_Hybrid_Angular_and_CVPR_2025_paper.html)

### Real-world and Mixed Datasets

- **NYU Depth V2** (2012) - RGB-D indoor scenes. [Dataset](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html)
- **KITTI** (2012) - LiDAR data for autonomous driving. [Dataset](https://www.cvlibs.net/datasets/kitti/)
- **Paris-rue-Madame** (2014) - Mobile laser scanning data of an urban street. [Paper](https://doi.org/10.5220/0004934808190824)
- **S3DIS** (2016) - Large-scale indoor RGB-D scenes. [Dataset](http://buildingparser.stanford.edu/dataset.html)
- **SceneNN** (2016) - Indoor RGB-D scenes with reconstructed meshes. [Dataset](https://hkust-vgd.github.io/scenenn/)
- **MS Kinect** (2016) - Structured light and ToF scans with ground-truth normals. [Paper](https://doi.org/10.1145/2980179.2980232)
- **PERL** (2017) - Indoor point clouds collected with a Velodyne LiDAR. [Dataset](http://sites.google.com/site/nakjudoh/normnet.htm)
- **Semantic3D** (2017) - Large-scale terrestrial laser scans. [Dataset](http://www.semantic3d.net/)
- **ScanNet** (2017) - Annotated RGB-D indoor reconstructions. [Dataset](http://www.scan-net.org/)
- **PCV** (2019) - Mixed data for multi-normal estimation. [Paper](https://doi.org/10.1109/TVCG.2018.2827998)
- **WHU-TLS** (2020) - Large-scale terrestrial laser scanning benchmark. [Dataset](https://github.com/WHU-USI3DV/WHU-TLS)
- **Waymo Open Dataset** (2020) - Large-scale LiDAR data for autonomous driving. [Dataset](https://waymo.com/open/)

## Benchmarks and Evaluation
-----
### Metrics

- **RMSE** - Root mean squared angular error between estimated and ground-truth normals.
- **CND** - Chamfer normal distance, which re-establishes spatial correspondences before measuring angular error and is more robust to noisy point displacements.
- **PGP-alpha** - Proportion of good points whose angular error is below a threshold alpha; higher values indicate better performance.

### Evaluation Protocols

- **PCPNet Evaluation** - Synthetic evaluation on CAD-like and non-CAD-like shapes with controlled noise and sampling density.
- **FamousShape Evaluation** - Cross-shape evaluation on more complex iconic geometries.
- **ABC Evaluation** - Evaluation of generalization on CAD shapes.
- **SceneNN Evaluation** - Quantitative real-world evaluation using mesh-derived normal ground truth.
- **Semantic3D Evaluation** - Qualitative evaluation on large-scale real scans without normal ground truth.
- **Computational Requirements** - Comparison of inference time, model size, input patch size, and output normals per patch.

## Applications
-----
### Denoising

- **Low Rank** (Lu et al.) - *Low Rank Matrix Approximation for 3D Geometry Filtering*. TVCG 2022. [Paper](https://doi.org/10.1109/TVCG.2020.3026785)

### Surface Reconstruction

- **Poisson Surface Reconstruction** (Kazhdan et al.) - *Poisson Surface Reconstruction*. SGP 2006. [Paper](https://doi.org/10.2312/SGP/SGP06/061-070)
- **Screened Poisson Reconstruction** (Kazhdan and Hoppe) - *Screened Poisson Surface Reconstruction*. TOG 2013. [Paper](https://doi.org/10.1145/2487228.2487237)

### Registration

- **NICP** (Serafin and Grisetti) - *NICP: Dense Normal Based Point Cloud Registration*. IROS 2015. [Paper](https://doi.org/10.1109/IROS.2015.7353455)

## Future Directions
-----

- **Effective Unsupervised Learning** - Develop unified unsupervised frameworks that generalize across diverse inputs without shape-specific retraining.
- **Real-time Inferencing** - Design lightweight architectures for time-sensitive applications such as 3D Gaussian splatting and autonomous driving.
- **Cross-domain Adaptation** - Improve robustness to non-uniform density, sparsity, and noise in real-world scans through data augmentation and domain adaptation.
- **Foundation Models for Local Property Estimation** - Explore self-supervised pre-training on diverse point clouds and efficient cross-domain adaptation strategies for local geometric properties such as normals, metrics, and curvatures.
- **Multi-modal Data Fusion** - Integrate RGB images with point clouds to resolve geometric ambiguities and distinguish actual sharp edges from noise.

## Related Resources
-----

- [Survey paper](https://doi.org/10.1007/s41095-022-0305-5)
- [Official survey code repository](https://github.com/weijiawang96/awesome-3d-point-cloud-normal-estimation)
- [Awesome Point Cloud Registration](https://github.com/XuyangBai/awesome-point-cloud-registration)
- [Awesome 3D Point Cloud Denoising](https://github.com/agarnung/awesome-3d-point-cloud-denoising)
- [Awesome 3D Point Cloud Attacks](https://github.com/cuge1995/awesome-3D-point-cloud-attacks)