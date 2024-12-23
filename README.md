# ECE 603 Final Project Codebase
## Medical Image Enhancement Using CLAHE and Pelican Optimization

This project codebase documents the code for reproducing the results from the paper [A novel medical image enhancement algorithm based on CLAHE and pelican optimization](https://link.springer.com/article/10.1007/s11042-024-19070-6). We reproduce the results from this paper as well as extending upon it creating a meaningful extension. This paper uses contrast limited adaptive histogram equalization (CLAHE) and pelican optimization algorithm (POA) to enhance medical images. The extended works conducted by Umar and Purva focus on RGB images of histology slides and use a Resnet50 feature encoder for image enhancment. Here are some relevant links: [presentation link](https://youtu.be/vaNkmamVCnA) and [final report link]().

## Table of Contents
- [Overview](#abstract)
- [Directory Structure](#directory-structure)
- [Notebook Sections](#notebook-sections)
- [Installation](#installation)

---

## Abstract
This report reproduces works from Haddadi et al by investigating the integration
of Contrast-Limited Adaptive Histogram Equalization (CLAHE) with the Pelican
Optimization Algorithm (POA) for medical image enhancement. The original
methodology, applied to grayscale CT and MRI datasets, was reproduced using
synthetic images generated via Stable Diffusion. The approach optimizes CLAHE’s
clip limit parameter (β) using POA’s nature-inspired search mechanism, balancing
contrast enhancement with noise reduction. We extended upon this work by applying
a modified algorithm to RGB histology images; by adapting the optimization process
with ResNet50 feature encoding and a multi-objective loss function we enable
effective enhancement of texture-rich data. We were able to reproduce the results
from the original paper as well as demonstrate adequate performance across synthetic,
real world medical datasets, and histology images, achieving high PSNR and SSIM
values while preserving diagnostically relevant features. Despite dataset limitations
and computational complexity, the study highlights the potential of CLAHE-POA
for diverse imaging applications and suggests future work on optimization efficiency
and dataset diversity

---

## Directory Structure
```
ece-603-final-project-repo/
│
├── ECE_603_Final_Project_Code.ipynb.ipynb          # Main Jupyter Notebook
├── README.md                                       # Project documentation
├── requirements.txt                                # Python dependencies
└── histology_images/                               # Directory for storing histology images
```


---

## Notebook Sections

- **Preamble**: Package installation and imports
- **Reproducing Algorithm Results**: Calculate PSNR, SSIM, Entropy, MSE, CoC, and Standard Deviation for both original and enhanced images.
  - **Data Generation**: Generate grayscale medical images using Stable Diffusion.
  - **Algorithm Implementation**: Implement the `PelicanOptimizer` as per the original paper.
  - **Reproducing Results**: Conducting same analysis from original paperthrough bar plots and line plots.
- **Extension of Paper**: Implement the `FeatureExtracterPelicanOptimizer` as per the extended works
- **Comperative Analysis**: Comparing results against other state-of-the-art models.

---

## Installation

1. Clone this repository:
```
 git clone https://github.com/gitUmaru/ece-603-final-project-repo.git
cd ece-603-final-project-repo/
```
2. Install the required dependencies:
```
pip install -r requirements.txt
```
3. Open and run the cells in the `ECE_603_Final_Project_Code.ipynb` notebook

---

## Methods


<div align="center" style="width: 80%; margin: auto;">
  <img src="https://github.com/user-attachments/assets/143d2cf1-2c71-4801-8877-ddb990ff85f1" alt="Image 1" style="width: 75%; height: auto;">
  
  Methods of original paper after image generation, showing $\beta$ estimation and finding optimal $\beta$ using POA

<div align="center" style="width: 80%; margin: auto; margin-top: 20px;">
  <img src="https://github.com/user-attachments/assets/62de0edc-ceb0-457d-a5e9-8290d8d616e5" alt="Image 2" style="width: 80%; height: auto;">

  Methods of extended works by enhancing each colour channel seperately and then finding optimal $\beta$ for downstream CLAHE.
</div>

## Results

<div align="center" style="width: 80%; margin: auto;">
  <img src="https://github.com/user-attachments/assets/3269f871-a4c5-4961-9763-d42276e9027f" alt="Image 1" style="width: 50%; height: auto;">
  
  Comparison of image enhancement results. Images (a) and (b) represent reproduction results from the original study using our code.
</div>

<div align="center" style="width: 80%; margin: auto; margin-top: 20px;">
  <img src="https://github.com/user-attachments/assets/2accb2bd-bc97-4c5b-a223-67c051c89926" alt="Image 2" style="width: 55%; height: auto;">

  <b>(Left)</b> Original image from the Bach Breast Cancer Histology dataset and <b>(Right)</b> Enhanced image using the extended algorithm
</div>


