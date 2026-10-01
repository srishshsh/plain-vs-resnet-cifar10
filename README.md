# Plain vs. Residual CNNs on CIFAR-10

Comparison of plain and residual convolutional neural networks implemented from scratch in NumPy on the CIFAR-10 dataset.

## Project Overview

This project investigates whether residual shortcut connections improve the trainability and validation performance of convolutional neural networks as network depth increases.

Plain CNNs and residual CNNs were evaluated across different depths using a controlled experimental setup on CIFAR-10.

The models were implemented from scratch in NumPy, including convolutional layers, activation functions, pooling, dense layers, dropout, softmax cross-entropy, SGD, and manual backward passes.

## Key Questions

- How does increasing network depth affect model performance?
- Do residual shortcut connections improve performance at greater depths?
- How do residual connections affect training and gradient propagation?

## Dataset

**CIFAR-10** contains 60,000 32×32 colour images across 10 object classes.

- 40,000 training images
- 10,000 validation images
- 10,000 test images

## Experimental Setup

The study compares:

- Plain CNN architectures
- Residual CNN architectures
- 1–4 two-convolution blocks per stage

Residual connections were implemented using identity shortcuts when dimensions matched and projection shortcuts when spatial dimensions or channel numbers changed.

The residual backward pass was additionally verified using numerical gradient checks.

## Results

Residual models showed modestly higher peak validation accuracy at intermediate depths:

| Blocks per stage | Plain CNN | Residual CNN |
| ---------------- | --------: | -----------: |
| 1                |    60.58% |       58.67% |
| 2                |    57.19% |       58.55% |
| 3                |    56.57% |       57.66% |
| 4                |    57.28% |       56.27% |

The selected shallow plain CNN achieved a peak validation accuracy of **62.64%** and a final test accuracy of **61.56%** after learning-rate selection and extended training.

---------------------------------------------------------------------------------------------------------------------------------------

My contribution to the project was the creation of the technical report, including the documentation, analysis, and interpretation of the experimental setup and results.

The project source code can be provided upon request.
