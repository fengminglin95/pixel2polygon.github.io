# From Pixels to Polygons: A Survey of Deep Learning Approaches for Medical Image‑to‑Mesh Reconstruction

This page summarises the article **"From Pixels to Polygons: A Survey of Deep Learning Approaches for Medical Image‑to‑Mesh Reconstruction"**. The survey provides a comprehensive review of deep learning techniques that directly reconstruct 3D meshes from medical images, discussing methodological categories, evaluation metrics, publicly available datasets and future research directions【487778023697178†L52-L70】.  

## Abstract Overview

Deep learning has enabled direct conversion of medical scans into volumetric meshes, which are essential for digital twins and in‑silico simulations. The paper groups existing approaches into four broad categories: **template models**, **statistical shape models**, **generative models**, and **implicit models**【487778023697178†L52-L70】. Each category is further subdivided by the type of input processing and output representation, covering multi‑modality imaging such as computed tomography (CT), magnetic resonance imaging (MRI) and ultrasound. The authors discuss challenges such as topological correctness, geometric accuracy and multi‑modality integration, review common distance metrics, regularisation terms and clinically driven evaluation metrics, and summarise publicly available datasets. Future research directions include high‑fidelity simulation, topological constraints and multi‑model fusion for clinical applications【487778023697178†L52-L70】.

## Authors and Affiliation

- **Fengming Lin et al.** – Centre for Image Computing & Modelling and departments of Medicine Engineering & Physics at the University of Manchester.
- Published on 6 May 2025 (arXiv:2505.03599).

## Key Figures from the Paper

The following images originate from the paper and illustrate different concepts and frameworks. Click an image to view a larger version.

### Figure 1: In‑silico trial pipeline

![IST_pipeline4](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/fig/IST_pipeline4.png)

*Figure 1 explanation*: This pipeline illustrates four stages from medical imaging (CT, MR) to digital twin anatomies, virtual population generation and computational simulation, with examples of cerebral aneurysm flow diverter and transcatheter heart valve.

### Figure 2: PRISMA literature workflow

![PRISMA](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/fig/PRIMAv1.png)

*Figure 2 explanation*: The PRISMA flow diagram summarises the systematic review process: identification of records, deduplication, screening, eligibility assessment and inclusion of studies.

### Figure 3: Methods taxonomy

![Taxonomy](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/x1.png)

*Figure 3 explanation*: The taxonomy summarises medical image‑to‑mesh reconstruction research along four dimensions—input modality, method type, output representation and losses/metrics—and highlights 12 submodules: conditional deformation models, registration models, linear/non‑linear statistical shape models, VAE, GAN, interpolation models, diffusion models, signed distance function (SDF) models, neural ordinary differential equation (ODE) models, occupancy function models and NeRF models.

### Figure 4: Conditional deformation model

![DeformationModel1](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/fig/Deformation_Model_1.png)

*Figure 4 explanation*: A conditional deformation model uses a convolutional neural network (CNN) to extract image features and a graph neural network (GNN) to map a template mesh to the target mesh through predicted vertex displacements.

### Figure 5: Template registration model

![DeformationModel4](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/fig/Deformation_Model_4.png)

*Figure 5 explanation*: Registration models employ a CNN to predict a deformation field between the image and the template, warping the template mesh to match the target.

### Figure 6: Linear statistical shape model

![SSM1](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/fig/SSM1.png)

*Figure 6 explanation*: Linear statistical models use principal component analysis to learn shape bases and predict shape coefficients from images via CNNs, reconstructing the mesh as a linear combination of bases.

### Figure 7: Non‑linear statistical shape model

![SSM2](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/fig/SSM2.png)

*Figure 7 explanation*: Non‑linear statistical models employ CNN encoders to extract latent variables from the mesh and the image separately and decode them jointly into a mesh.

### Figure 8: Variational autoencoder (VAE) generative model

![VAEModel](https://ar5iv.labs.arxiv.org/html/2505.03599/assets/x2.png)

*Figure 8 explanation*: A VAE encodes the image as distribution parameters, samples a latent vector and decodes it into a point cloud that is subsequently converted into a mesh.

## Method Categories

| Category | Representative methods | Key characteristics |
| --- | --- | --- |
| **Template models** | MeshDeformNet, Voxel2Mesh, HeartFFDNet, PialNN, etc. | Iteratively deform a template mesh by predicting vertex displacements to approximate the target shape; CNNs or GNNs extract image features and predict the deformation field. |
| **Statistical shape models** | Linear/non‑linear SSM | Use PCA or deep networks to learn a shape basis and coefficients, establishing a mapping between the input image and the shape space; incorporate prior shape constraints during reconstruction. |
| **Generative models** | VAE models, GAN models, interpolation models, diffusion models | Directly generate a point cloud or mesh from the image using generator–discriminator architectures, interpolation networks or diffusion processes without relying on a template or explicit shape space. |
| **Implicit models** | SDF, neural ODE, occupancy function, NeRF models | Represent 3D geometry via implicit functions such as signed distance functions or occupancy fields, learn a mapping from images to these functions and extract meshes from the learned implicit field. |

## Evaluation Metrics and Datasets

| Category | Common metrics | Description |
| --- | --- | --- |
| **Similarity/Distance** | Chamfer distance, Hausdorff distance, point‑to‑surface distance | Measure the distance between the reconstructed mesh and the ground‑truth mesh in vertex space, reflecting geometric accuracy. |
| **Regularisation & Topology** | Surface smoothness, curvature, topology consistency penalties | Encourage smooth surfaces, enforce correct mesh topology and suppress noise. |
| **Function‑driven metrics** | Clinical measurement error, volumetric error, simulation accuracy | Evaluate the mesh in downstream clinical tasks such as computing anatomical measurements or running simulations. |

Public datasets span cardiac, cerebral, vascular and skeletal anatomies with imaging modalities including CT, MR and ultrasound. Commonly used datasets include the MGH brain aneurysm dataset, ADNI Alzheimer’s dataset, UK Biobank cardiac dataset and MICCAI challenge datasets. The survey summarises the number of samples and applicable tasks for each dataset.

## Citation

Lin, F., Zakeri, A., Xue, Y., et al. *From Pixels to Polygons: A Survey of Deep Learning Approaches for Medical Image‑to‑Mesh Reconstruction*. arXiv preprint, 2025【487778023697178†L52-L70】.
