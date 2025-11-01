# 🩺 HyperKvasir Polyp Detection using YOLOv5s

This project focuses on **polyp detection in endoscopic (colonoscopy) images** using the **HyperKvasir dataset**.  
We compare a **pretrained YOLOv5s** model against a **customized YOLOv5s** model that includes **anchor optimization, hyperparameter tuning, and data augmentation** to improve detection accuracy.

---

## 📘 Overview

Early detection of colorectal polyps is crucial for preventing colorectal cancer.  
Using deep learning–based object detection (YOLOv5s), this project aims to automatically identify and localize polyps in endoscopic images to assist gastroenterologists in diagnosis and screening.

---

## 🧠 Objectives

- Train a **pretrained YOLOv5s** model on the HyperKvasir dataset as a baseline.  
- Develop a **custom YOLOv5s** model with:
  - Optimized anchors
  - Tuned hyperparameters
  - Extended training epochs
  - Data augmentation  
- Compare both models on key metrics: **Precision, Recall, mAP@0.5, and mAP@0.5:0.95**

---

## 🗂️ Dataset

**Dataset:** [Kvasir-SEG (HyperKvasir) on Kaggle](https://www.kaggle.com/datasets/debeshjha1/kvasirseg)  
Contains endoscopic images with corresponding segmentation masks for polyps.  

---

## ⚙️ Model Architecture

**Model:** YOLOv5s  
- Backbone: CSPDarknet-based  
- Neck: PANet for feature aggregation  
- Head: YOLO detection layers  
- Framework: PyTorch  

Custom modifications include:
- Anchor box optimization (using `autoanchor=True`)
- Hyperparameter tuning (LR, momentum, augmentation)
- Longer training with early stopping
- Augmentations: mosaic, hsv, flipping, scaling

---

## 📊 Results

| Model | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 |
|--------|------------|--------|----------|---------------|
| YOLOv5s Pretrained (Train/Val) | 0.9167 | 0.8853 | 0.9552 | 0.7897 |
| YOLOv5s Pretrained (Test) | 0.8924 | 0.8773 | 0.9358 | 0.7624 |
| YOLOv5s Custom (Train/Val) | 0.919 | 0.920 | 0.961 | 0.781 |
| YOLOv5s Custom (Test) | 0.9434 | 0.9486 | 0.9758 | 0.7942 |

✅ **Custom YOLOv5s** outperformed the pretrained model, showing clear gains in detection precision and recall.

---

## 🧩 Project Structure

