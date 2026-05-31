
# 🦴 Bone Disease Classification Using Deep Learning

> Deep learning-based classification of knee X-ray images into **Normal**, **Osteopenia**, and **Osteoporosis** using a DINOv2 + Attention-Based Multiple Instance Learning (AB-MIL) framework.

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Research-purple)

---

## 📋 Overview

This project focuses on the **automated classification of bone diseases** from knee X-ray images using deep learning. Multiple architectures were implemented and compared to identify the most effective approach for three-class prediction.

---

## 🎯 Target Classes

| Class | Description |
|---|---|
| ✅ Normal | Healthy bone condition |
| ⚠️ Osteopenia | Reduced bone density |
| 🚨 Osteoporosis | Severe bone density loss |

---

## 🧠 Models Explored

### 1. Custom CNN *(Baseline)*
A custom CNN designed and trained from scratch. Learns hierarchical image features directly from knee X-ray images.

### 2. DenseNet *(Improved)*
Dense connectivity between layers improves feature propagation and reuse, achieving better representation learning than the baseline CNN.

### 3. DINOv2 + AB-MIL *(Proposed)*
Combines a **self-supervised Vision Transformer (DINOv2)** with an **Attention-Based Multiple Instance Learning** framework for superior classification and interpretability.

| Model | Type | Interpretability |
|---|---|---|
| Custom CNN | Baseline | ❌ |
| DenseNet | Improved | ❌ |
| **DINOv2 + AB-MIL** | **Proposed ✦** | **✅ Attention heatmaps** |

---

## ⚙️ Methodology Pipeline

```
Input Knee X-rays
        ↓
Image Preprocessing
(Resize → Normalization → Gaussian Filter → Augmentation)
        ↓
Patch Generation
(Fixed-grid patch split)
        ↓
Feature Extraction
(DINOv2 Vision Transformer)
        ↓
AB-MIL Aggregation
(Attention-weighted pooling)
        ↓
Classification Head
(Softmax → 3 classes)
        ↓
Output Prediction + Attention Heatmaps
```

### Preprocessing Steps
- Image resizing and min-max normalization
- Bilinear interpolation and noise reduction
- Gaussian filtering
- Data augmentation and geometric transformations

---

## 📂 Dataset

Knee X-ray images collected from publicly available medical imaging repositories.

- **Classes:** Normal, Osteopenia, Osteoporosis
- **Augmentation:** Applied to improve generalization and reduce class imbalance

---

## 🛠️ Technologies Used

| Category | Tools |
|---|---|
| Deep Learning | PyTorch, TensorFlow |
| Computer Vision | OpenCV, DINOv2 |
| Architectures | Custom CNN, DenseNet, AB-MIL |
| Utilities | NumPy, Matplotlib |
| Language | Python 3.8+ |

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/your-username/bone-disease-classification.git
cd bone-disease-classification

# Install dependencies
pip install -r requirements.txt

# Run training
python train.py --model dinov2_abmil --epochs 50

# Run inference
python predict.py --image path/to/xray.jpg
```

---

## 📊 Experimental Evaluation

| Metric | Custom CNN | DenseNet | DINOv2 + AB-MIL |
|---|---|---|---|
| Accuracy | — | — | **—** |
| Precision | — | — | **—** |
| Recall | — | — | **—** |
| F1-Score | — | — | **—** |

> 📌 Fill in results after training.

---

## 🔍 Interpretability

Attention heatmaps visualize the image regions most contributing to the final prediction, providing clinically meaningful transparency into the model's decision process.

---

## 📁 Project Structure

```
bone-disease-classification/
├── data/
│   ├── raw/
│   └── processed/
├── models/
│   ├── cnn.py
│   ├── densenet.py
│   └── dinov2_abmil.py
├── utils/
│   ├── preprocessing.py
│   ├── augmentation.py
│   └── metrics.py
├── train.py
├── predict.py
├── requirements.txt
└── README.md
```

---

## 🔭 Future Work

- [ ] Training on larger medical imaging datasets
- [ ] Explainable AI improvements for clinical trust
- [ ] Multi-modal medical diagnosis systems
- [ ] Clinical validation and deployment
- [ ] Integration with DICOM imaging workflows

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- [DINOv2](https://github.com/facebookresearch/dinov2) by Meta AI Research
- Publicly available knee X-ray imaging datasets
- Attention-Based Deep Multiple Instance Learning (Ilse et al., 2018)
```
