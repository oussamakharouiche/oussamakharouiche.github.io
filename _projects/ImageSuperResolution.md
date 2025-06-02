---
layout: project
title: "Image Super-Resolution with Conditional Diffusion"
---

**A personal project implementing an image super-resolution model using a conditional diffusion approach.**

---

## Presentation

This project explores the application of conditional diffusion models to the task of image super-resolution. By leveraging a diffusion-based generative process conditioned on low-resolution inputs, the model learns to reconstruct high-fidelity images at four times the original resolution. The implementation is based on PyTorch and demonstrates how conditional diffusion can produce sharper and more realistic outputs compared to traditional upsampling methods.

---

## Overview

- **Dataset**: We utilize the DIV2K dataset, which contains high-quality 2K resolution images.
- **Preprocessing**:
  1. Each image is downsampled to 256x256 using bicubic downsampling.
  2. For each patch, a 64×64 low-resolution version is created by bicubic downsampling.
  3. A bicubic upsampled 256×256 image is used as the conditioning input for the diffusion model.
- **Task**: Super-resolve from 64×64 to 256×256 pixels.
- **Conditioning**: The model is conditioned on the bicubic upsampled image to guide the diffusion process toward plausible high-frequency details.

---

## Technologies Used

- **PyTorch**: Deep learning framework for building and training the diffusion model.
- **Pillow**: Image processing library for loading, transforming, and saving images.
- **Vast.ai**: Cloud GPU provider for scalable and cost-effective training.

---

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/oussamakharouiche/image-super-resolution.git
   cd image-super-resolution
   ```
2. Create a virtual environment and install dependencies:
   ```bash
   python3 -m venv superres
   source superres/bin/activate
   pip install -r requirements.txt
   ```

---

## Usage

1. Generate the dataset:
   ```bash
   python3 prepare_dataset.py --low 64 --high 256
   ```
2. Train the Super Resolution model:
   ```bash
   python3 train.py 
   ```
3. evaluate the Super Resolution model on the test data:
   ```bash
   python3 evaluate.py 
   ```

---

## Results


Below are examples comparing the real low-resolution input, the bicubic upsample, the model output, and the ground-truth high-resolution image.

| Low-Res Input (64×64)                                                                        | Bicubic Upsample                                                                                   | Model Output                                                                                      | Ground Truth (256×256)                                                                          |
|:--------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------:|
| ![lowres]({{ site.baseurl }}/_images/lowres/0030.png)                                | ![bicubic]({{ site.baseurl }}/_images/bicubic/0030.png)                                   | ![superres]({{ site.baseurl }}/_images/superres/0030.png)                                | ![gt]({{ site.baseurl }}/_images/ground_truth/0030.png)                                 |
|:--------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------:|
| ![lowres]({{ site.baseurl }}/_images/lowres/0185.png)                                | ![bicubic]({{ site.baseurl }}/_images/bicubic/0185.png)                                   | ![superres]({{ site.baseurl }}/_images/superres/0185.png)                                | ![gt]({{ site.baseurl }}/_images/ground_truth/0185.png)                                 |


Our initial results are promising, especially considering the model's large size of approximately **280 million parameters**. It was trained on a relatively small dataset of **720 images from DIV2K**, with 80 images reserved for testing.

To further enhance the model's performance and generalizability, our next steps will focus on:

* **Data Augmentation:** Implementing techniques such as random cropping, random flips, random rotations, and color jittering during training.
* **Dataset Expansion (Natural Images):** Incorporating additional datasets featuring natural imagery, similar to those found in DIV2K.
* **Generalization Testing:** Adding diverse datasets to thoroughly evaluate the model's ability to generalize.


---

## Bibliography
1. [**Image Super-Resolution via Iterative Refinement**](https://arxiv.org/abs/2104.07636).
2. [**Large Scale GAN Training for High Fidelity Natural Image Synthesis**](https://arxiv.org/abs/1809.11096).
3. [**Denoising Diffusion Probabilistic Models**](https://arxiv.org/abs/2006.11239).
4. [**Deep Unsupervised Learning using Nonequilibrium Thermodynamics**](https://arxiv.org/abs/1503.03585).

---

🔗 **Links**  
- [GitHub Repository](https://github.com/oussamakharouiche/image-super-resolution)

