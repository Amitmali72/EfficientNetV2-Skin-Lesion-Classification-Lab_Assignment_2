# EfficientNetV2-Skin-Lesion-Classification (Lab Assignment 2)

## 🧠 EfficientNetV2-Based Multiclass Skin Lesion Classification

## 📌 Overview

This project focuses on multiclass classification of skin lesions using a transfer learning approach with EfficientNetV2-Small trained on the HAM10000 dataset.

Training was performed in two phases:

1. Feature Extraction – Backbone frozen  
2. Fine-Tuning – Top layers partially unfrozen for domain adaptation  

---

## 🏗 Model Architecture

- Backbone: EfficientNetV2-S (pretrained on ImageNet)  
- Input Size: 224 × 224  
- Global Average Pooling Layer  
- Dropout: 0.3  
- Output Layer: Dense (7-class Softmax activation)  

---

## 📊 Dataset Details

### HAM10000 (Human Against Machine 10000)

- Total Images: 10,015  
- Number of Classes: 7  

### Classes:
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
- Loss Function: Categorical Crossentropy  
- Data Augmentation:
  - Random Rotation  
  - Zoom  
  - Horizontal Flip  
- Fine-Tuning: Top 30% of layers unfrozen  

---

## 📈 Results Summary

| Model Stage | Validation Accuracy |
|-------------|--------------------|
| Feature Extraction | ~67% |
| Fine-Tuned Model | ~66–68% |
| Reported Research Accuracy | 88.62% |

---

## 📉 Performance Gap Analysis

The observed performance gap compared to the reported research result (88.62%) may be attributed to:

- Significant class imbalance (major dominance of “nv” class)  
- Fewer training epochs  
- Limited data augmentation techniques  
- Minimal hyperparameter optimization  
- Hardware constraints limiting extensive experimentation  

---

## 🔎 Key Findings

- Model predictions were biased toward the majority class.  
- Fine-tuning resulted in marginal performance improvement.  
- Transfer learning effectively captured meaningful dermatological features.  

---

## 🛠 Required Libraries
-tensorflow
-numpy
-pandas
-matplotlib
-seaborn
-scikit-learn

