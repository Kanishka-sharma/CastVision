# CastVision: CNN-Based Defect Detection in Metal Castings

**CastVision** is a deep learning model built using **Convolutional Neural Networks (CNNs)** to automatically detect **defects in metal casting images**.  
It distinguishes between **defective** and **non-defective** castings, helping automate visual inspection in manufacturing.

---

## Overview

Manual inspection of metal castings is time-consuming and error-prone. CastVision leverages deep learning and computer vision to identify casting defects quickly and accurately, reducing human bias and improving production quality.

---

## Technical Details

- **Frameworks:** TensorFlow, Keras, OpenCV  
- **Languages:** Python  
- **Libraries:** NumPy, Matplotlib, Seaborn, scikit-learn  
- **Input Size:** 128×128 RGB images  
- **Model Type:** Binary classification (`def_front` vs `ok_front`)  

---

## Methodology

### 1. Preprocessing
- Images resized to **128×128**
- Normalized pixel values (`/255`)
- Edge and contour mapping using OpenCV for defect visualization

### 2. Data Augmentation
Applied random rotation, zoom, horizontal flip, and translation to enhance training diversity.

### 3. CNN Architecture

| Layer | Details |
|:------|:---------|
| Conv2D (32 filters, 3×3) + ReLU | Feature extraction |
| MaxPooling2D | Downsampling |
| Conv2D (64 filters, 3×3) + ReLU | Deep features |
| MaxPooling2D | Downsampling |
| Conv2D (64 filters, 3×3) + ReLU | Fine-grained patterns |
| Flatten + Dense(64, ReLU) | Classification head |
| Dense(1, Sigmoid) | Binary output |

**Loss:** Binary Crossentropy | **Optimizer:** Adam | **Metric:** Accuracy  

---

## Model Performance

| Metric | Score |
|:-------|:-------|
| Validation Accuracy | **97.20%** |
| Validation Loss | 0.0986 |
| Test Accuracy | **97.20%** |

### Classification Report
| Class | Precision | Recall | F1-Score |
|:------|:-----------|:--------|:----------|
| Defective | 1.00 | 0.96 | 0.98 |
| Non-Defective | 0.93 | 1.00 | 0.96 |
| **Overall Accuracy** | **0.97** | - | - |

---

## Insights

- The CNN effectively distinguishes casting defects with minimal false positives.  
- OpenCV contour visualization confirms that edges and cracks align with defect regions.  
- The model generalizes well, achieving strong accuracy without transfer learning.

---

## Future Enhancements

- Integrate **Grad-CAM** for model interpretability  
- Experiment with **ResNet50 or MobileNetV2** for improved performance  
- Develop a **Streamlit-based web app** for real-time inspection  
- Optimize model using **TensorFlow Lite** for on-device deployment  

---

> CastVision proves that deep learning can revolutionize industrial quality control - turning traditional inspection into intelligent automation.
