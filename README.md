# 🦁 YOLOv8s Animal Detection on 21-Class Custom Dataset

This repository presents the training and evaluation of a **YOLOv8s** object detection model on a **custom 21-class animal dataset**, including species like **Cattle, Goat, Sheep, Chicken, Duck**, and more. The goal is accurate localization and classification of diverse animals in natural environments.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CIc1J-woBaxiHKT4OCKy6klOyl6fez9J?usp=sharing)

>  "Cattle", "Goat", "Sheep", "Chicken", "Duck", "Pig", "Horse", "Rabbit", "Tiger", "Leopard", "Fox", "Bear", "Snake", "Lizard", "Dog", "Eagle", "Mouse", "Monkey", "Porcupine", "Elephant", "Reptile"

---

## 📁 Dataset Overview

- **Number of Classes**: 24 animal species
- **Label Format**: YOLO (normalized `[x_center, y_center, width, height]`)
- **Annotation Distribution**:

![Label Distribution and Box Positions](/Performance-yolov8s/labels.jpg)

- **Pairwise Feature Distribution (Correlogram)**:

![Bounding Box Correlogram](/Performance-yolov8s/labels_correlogram.jpg)

---

## 🚀 Model: YOLOv8s

- **Framework**: Ultralytics YOLOv8
- **Model**: YOLOv8s (Small variant)
- **Training Duration**: 50 epochs
- **Losses Monitored**: Bounding box loss, classification loss, distribution focal loss (DFL)

### 🧪 Sample Training Batches

<p align="center">
  <img src="./Performance-yolov8s/train_batch0.jpg" width="30%">
  <img src="./Performance-yolov8s/train_batch1.jpg" width="30%">
  <img src="./Performance-yolov8s/train_batch2.jpg" width="30%">
</p>

---

## 📈 Training Performance

![Training Metrics Overview](/Performance-yolov8s/results.png)

- Significant improvement in:
  - **Precision**
  - **Recall**
  - **mAP@0.5** and **mAP@0.5:0.95**
- Loss curves (box, cls, dfl) show consistent decrease, indicating healthy convergence.

---

## 📊 Metric Curves

<p align="center">
  <img src="./Performance-yolov8s/BoxPR_curve.png" width="45%">
  <img src="./Performance-yolov8s/BoxF1_curve.png" width="45%">
</p>

---

## 🔍 Confusion Matrix

| Raw Confusion Matrix | Normalized Confusion Matrix |
|----------------------|-----------------------------|
| ![Raw](/Performance-yolov8s/confusion_matrix.png) | ![Normalized](/Performance-yolov8s/confusion_matrix_normalized.png) |

- Good separation among most classes.
- Minor confusion among similar species (e.g., Goat vs. Sheep).

---

## 🖼️ Validation Results

Visual comparisons of ground truth and predictions:

| Ground Truth | Prediction |
|--------------|------------|
| ![](/Performance-yolov8s/val_batch0_labels.jpg) | ![](/Performance-yolov8s/val_batch0_pred.jpg) |
| ![](/Performance-yolov8s/val_batch1_labels.jpg) | ![](/Performance-yolov8s/val_batch1_pred.jpg) |
| ![](/Performance-yolov8s/val_batch2_labels.jpg) | ![](/Performance-yolov8s/val_batch2_pred.jpg) |

---

## ✅ Highlights

- ✅ Trained on a **balanced, multi-species animal dataset**
- 📈 Achieved **high accuracy and generalization**
- 🔍 Minimal confusion between classes
- 🧠 Precise bounding box prediction across object sizes
- 🔄 Future-ready for YOLOv8m/l/x scaling or real-time deployment

---

## 📚 Future Enhancements

- Address **class imbalance** for low-frequency species
- Train on **YOLOv8m/l/x** for improved accuracy
- Integrate **real-time inference pipeline**
- Experiment with **augmentation and hyperparameter optimization**
