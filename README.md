# 🛠️ CastVision: Defect Detection in Metal Castings
## 📘 Project Overview

This project implements an automated defect detection system for casting images using computer vision and deep learning. The system identifies whether a casting is **defective or non-defective** by analyzing image features using both **OpenCV-based contour analysis** and a **Convolutional Neural Network (CNN)**.

---

## 📂 Dataset

- The dataset consists of metal casting images labeled as **"def_front"** (defective) and **"ok_front"** (non-defective).
- The data is organized into `train` and `test` folders, each containing two classes.
- Total:
  - **Training images**: 6,633  
  - **Testing images**: 715  
- Image size: Resized to **128×128** or **200×200** depending on the stage.

---

## 🧹 Preprocessing & Visualization

- Applied **Gaussian Blur**, **Canny edge detection**, and **contour drawing** using OpenCV for visual inspection of surface anomalies.
- Preprocessing included:
  - Image normalization
  - Resizing
  - Data augmentation: rotation, flipping, shifting
- Visualization was done using `matplotlib` to show original vs. contoured images.

---

## 🤖 Model Architecture

Implemented a CNN using TensorFlow/Keras:

- **Conv2D + MaxPooling** layers to extract spatial features
- **Flatten + Dense** layers for classification
- **Sigmoid activation** for binary classification

```python
Conv2D(32) → MaxPool → Conv2D(64) → MaxPool → Conv2D(64) → Flatten → Dense(64) → Dense(1)

