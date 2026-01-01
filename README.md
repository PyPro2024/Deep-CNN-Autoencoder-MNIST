# Deep-CNN-Autoencoder-MNIST
# Deep CNN Autoencoder for Image Reconstruction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview
This project implements and compares distinct **Convolutional Autoencoder** architectures to reconstruct handwritten digits from the MNIST dataset. 

The goal was to analyze how increasing the depth of the encoder/decoder network affects the reconstruction quality and the Mean Squared Error (MSE) loss. The project demonstrates a progression from a shallow architecture to a deeper, optimized CNN capable of capturing fine-grained spatial hierarchies.

## 🚀 Key Features
- **Data Preprocessing:** Normalization and channel dimension expansion for CNN compatibility.
- **Architecture 1 (Baseline):** A shallow network with 1 encoder block and 1 decoder block.
- **Architecture 2 (Optimized):** A deep network with 3 encoder/decoder blocks using a bottleneck latent space.
- **Visualization:** Side-by-side comparison of original vs. reconstructed input.
- **Metric Tracking:** Utilization of Binary Crossentropy for training and MSE for evaluation.

## 🛠️ Tech Stack
- **Deep Learning:** TensorFlow, Keras (Layers: Conv2D, MaxPooling2D, UpSampling2D)
- **Data Manipulation:** NumPy
- **Visualization:** Matplotlib

## 📊 Results & Analysis

### Architecture Comparison
I experimented with two distinct architectures to minimize reconstruction loss.

| Model | Architecture Details | Performance |
|-------|----------------------|-------------|
| **Baseline** | Shallow Conv2D (32/64 filters) + MaxPooling | High Loss / Blurry edges |
| **Deep Network** | 3-Block Deep CNN (32/64/128 filters) | **MSE: ~0.0003** (High Fidelity) |

*Note: The deeper architecture significantly outperformed the baseline, reducing the MSE from ~8.12 (initial trials) to ~0.0003, demonstrating the importance of network depth in feature extraction.*

### Visualization
Below is the reconstruction output from the optimized deep model:

*(Note: If you have a screenshot of your final plot, drag and drop it here in the GitHub editor to display it)*

## 🧠 Model Architecture (Deep Version)
The final optimized model utilizes a symmetrical "Hourglass" structure:

1.  **Encoder:**
    * 3 Blocks of `Conv2D` + `MaxPooling2D`.
    * Compresses input (28x28) down to a latent space representation (7x7).
2.  **Bottleneck:**
    * High-dimensional feature extraction (128 filters).
3.  **Decoder:**
    * 3 Blocks of `Conv2D` + `UpSampling2D`.
    * Reconstructs the latent features back to original dimensions (28x28).

## 💻 Usage

1. Clone the repository:
   ```bash
   git clone [https://github.com/yourusername/Deep-CNN-Autoencoder-MNIST.git](https://github.com/yourusername/Deep-CNN-Autoencoder-MNIST.git)
