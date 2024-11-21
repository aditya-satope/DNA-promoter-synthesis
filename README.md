# DNA Promoter Synthesis using WGAN with Attention Mechanism

## Overview

The primary objective of this project is to investigate promoter structures and develop a methodology for synthesizing promoters that is both cost-effective and efficient compared to traditional lab-based synthesis methods. Promoters play a crucial role in initiating transcription, thereby influencing gene expression. This readme provides an overview of the project, including data selection, preprocessing techniques, deep learning models employed, promoters' generation, and evaluation methods.

## What I Learned

Throughout this research project, I gained valuable insights into several key areas:

- **Data Mining:** Finding the appropriate organism and its dataset proved to be a challenging endeavor. It required extensive research and evaluation to identify the most suitable data source for our project.

- **Research and Problem-Solving:** Dealing with a complex problem like promoter synthesis taught me the importance of breaking it down into smaller, manageable tasks. By addressing each problem one at a time, I learned how to systematically approach and overcome challenges.

- **Utilizing GANs:** The use of Generative Adversarial Networks (GANs) introduced me to a powerful tool for generating synthetic data.

## Data Selection

The dataset utilized in this project comprises approximately 16,000 promoter sequences extracted from the Eukaryotic Promoter Database (EPD), focusing on Drosophila melanogaster. Drosophila melanogaster, commonly known as the fruit fly, serves as an ideal model organism in biomedical research due to its various advantages such as ease of cultivation, short life cycle, and genetic manipulability.

## Preprocessing

Data preprocessing is a crucial step in preparing the raw data for subsequent analysis. The following techniques were applied:

### 1. Removing Duplicates

Multiple sequence alignment was performed to identify and eliminate duplicated sequences within the dataset.

### 2. Length and Character Checking

Ensured uniform length and valid base pairs (A, C, G, T) across all promoter sequences.

### 3. Encoding

One-hot encoding was employed to transform DNA sequences into a numerical matrix representation, facilitating machine and deep learning model training.


![image](https://github.com/aditya-satope/DNA-promoter-synthesis/assets/103871024/b719375b-1546-4d7b-b474-019e47e17ee3)


## Deep Learning Models

Two generative models were utilized for promoter synthesis:

### 1. DCGAN (Deep Convolutional Generative Adversarial Network)

#### Generator
- Consists of seven layers of transposed convolution followed by two convolution layers.
- Each transposed convolution layer is accompanied by a spectral norm layer for normalization.
- Utilizes two self-attention layers after every three transposed convolution layers.
  ![image](https://github.com/aditya-satope/DNA-promoter-synthesis/assets/103871024/352d9bfa-fead-41a0-a898-9c64e1fc4493)


#### Discriminator
- Comprises seven convolution layers, each followed by a spectral norm layer for normalization.
- Integrates two self-attention layers after every three convolution layers.
- Employs a Sigmoid activation function in the last layer for classifying natural and synthetic promoters.
  ![image](https://github.com/aditya-satope/DNA-promoter-synthesis/assets/103871024/6e509caf-9446-463e-8897-3434d14accb4)


### 2. WGAN-GP (Wasserstein Generative Adversarial Network with Gradient Penalty)

#### Generator
- Shares a similar architecture with DCGAN.
  
#### Critic (Discriminator)
- Utilizes instance normalization layers instead of spectral normalization layers.
- Opts against using Sigmoid as the final activation function.

## Promoters' Generation

Both DCGAN and WGAN-GP were trained to generate synthetic promoters based on the natural ones. Evaluation of the generated promoters involved sequence alignment and assessment of promoter activity scores using the Berkeley Drosophila Genome Project (BDGP).

## Evaluation and Filtration

### Sequence Alignment
- Multiple Sequence Alignment (MSA) was conducted to eliminate duplicate and redundant sequences.
- Pairwise Sequence Alignment compared the generated promoters with natural Drosophila promoters to ensure similarity.

### Promoter Activity
- BDGP was utilized to evaluate promoter activity based on specific motifs like the TATA box.
- Promoters with activity scores below the set threshold of 85% were filtered out from the dataset.


## Conclusion

The culmination of the project demonstrates significant progress in the synthesis of promoters. Particularly, the synthetic promoter identified as WGAN 525 exhibited superior performance compared to its natural counterpart, FP004187_Hsp70Ba_1. The promoter activity of FP004187_Hsp70Ba_1 was measured at 0.96, while the synthetic WGAN 525 achieved a higher promoter activity score of 0.98. This outcome underscores the efficacy of the methodology in generating promoters with enhanced functionality and efficiency. Moving forward, the advancements made in this project hold promise for revolutionizing gene expression studies and biotechnological applications, opening doors to novel avenues in synthetic biology.

This project aims to contribute to the field of synthetic biology by providing a more efficient method for synthesizing promoters, paving the way for advancements in gene expression studies and biotechnological applications.
