# EfficientNetV2-Skin-Lesion-Classification-Lab_Assignment_2

# # EfficientNetV2-Based Multiclass Skin Lesion Classification

## 📌 Overview

This project implements multiclass skin lesion classification using **EfficientNetV2-Small** with transfer learning on the HAM10000 dataset.

The model was trained in two stages:
1. Feature Extraction (frozen backbone)
2. Fine-Tuning (partially unfrozen layers)

---

## 🧠 Model Architecture

- Backbone: EfficientNetV2-S (ImageNet pretrained)
- Input Size: 224×224
- Global Average Pooling
- Dropout (0.3)
- Dense Layer (7-class Softmax)

---

## 📊 Dataset

**HAM10000 (Human Against Machine 10000)**  
- Total Images: 10,015  
- Number of Classes: 7  
  - akiec  
  - bcc  
  - bkl  
  - df  
  - mel  
  - nv  
  - vasc  

---

## 🚀 Training Strategy

- Optimizer: Adam  
- Loss: Categorical Crossentropy  
- Image Augmentation: Rotation, Zoom, Horizontal Flip  
- Fine-tuning: Top 30% layers unfrozen  

---

## 📈 Results Comparison

| Model | Validation Accuracy |
|-------|---------------------|
| Phase 1 (Feature Extraction) | ~67% |
| Fine-Tuned Model | ~66–68% |
| Research Paper Result | **88.62%** |

---

## 📉 Performance Gap Analysis

The lower accuracy compared to the research paper (88.62%) may be due to:

- Severe class imbalance (dominant “nv” class)
- Limited number of training epochs
- Basic augmentation strategy
- Limited hyperparameter tuning
- Reduced computational resources

---

## 🔬 Key Observations

- The model showed bias toward the majority class.
- Fine-tuning provided limited improvement.
- Transfer learning successfully extracted meaningful medical image features.

---

## 🛠 Requirements

```bash
tensorflow
numpy
pandas
matplotlib
seaborn
scikit-learn
