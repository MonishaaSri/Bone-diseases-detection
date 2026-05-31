# 🦴 Bone Disease Classification Using Deep Learning

> Deep learning-based classification of knee X-ray images into **Normal**, **Osteopenia**, and **Osteoporosis** using a DINOv2 + Attention-Based Multiple Instance Learning (AB-MIL) framework.

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Research-purple)

---

## 📋 Overview

This project focuses on the **automated classification of bone diseases** from knee X-ray images using deep learning. Multiple architectures were implemented and compared to identify the most effective approach for three-class prediction.

To identify the most effective approach, three models were implemented and evaluated — a custom CNN baseline, DenseNet, and the proposed DINOv2 + AB-MIL framework.

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
A custom Convolutional Neural Network designed and trained from scratch. Learns hierarchical image features directly from knee X-ray images.

### 2. DenseNet *(Improved)*
DenseNet was implemented to improve feature propagation and reuse through dense connectivity between layers, achieving better representation learning than the baseline CNN.

### 3. DINOv2 + AB-MIL *(Proposed)*
The final proposed architecture combines a **self-supervised Vision Transformer (DINOv2)** with an **Attention-Based Multiple Instance Learning** framework for improved feature extraction and interpretability.

| Model | Type | Feature Extraction | Interpretability |
|---|---|---|---|
| Custom CNN | Baseline | Convolutional layers | ❌ |
| DenseNet | Improved | Dense connectivity | ❌ |
| **DINOv2 + AB-MIL** | **Proposed ✦** | **Vision Transformer** | **✅ Attention heatmaps** |

---

## ⚙️ Methodology Pipeline

```
Input Knee X-rays
        │
        ▼
┌─────────────────────────────┐
│     Image Preprocessing     │
│  Resize → Normalization →   │
│  Gaussian Filter → Augment  │
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│      Patch Generation       │
│   Fixed-grid patch split    │
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│   Feature Extraction        │
│   DINOv2 Vision Transformer │
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│    AB-MIL Aggregation       │
│  Attention-weighted pooling │
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│     Classification Head     │
│   Softmax → 3 classes       │
└─────────────────────────────┘
        │
        ▼
Output Prediction + Attention Heatmaps
```

### Step-by-step breakdown

| Step | Operation | Details |
|---|---|---|
| 1 | **Input** | Knee X-ray images |
| 2 | **Preprocessing** | Resize, min-max normalization, bilinear interpolation, noise reduction, Gaussian filtering, augmentation, geometric transforms |
| 3 | **Patch generation** | Fixed-grid patch extraction for transformer input |
| 4 | **Feature extraction** | DINOv2 ViT extracts high-level patch representations |
| 5 | **AB-MIL** | Attention weights identify diagnostically relevant regions |
| 6 | **Classification** | Aggregated features passed to classification head |
| 7 | **Output** | Softmax prediction over 3 classes |
| 8 | **Interpretability** | Attention heatmaps highlight contributing image regions |

---

## 📂 Dataset

Knee X-ray images collected from publicly available medical imaging repositories.

- **Classes**: Normal, Osteopenia, Osteoporosis
- **Preprocessing**: Normalization, resizing, noise reduction
- **Augmentation**: Applied to improve generalization and address class imbalance

---

## 🛠️ Technologies Used

| Category | Tools |
|---|---|
| Deep Learning | PyTorch, TensorFlow |
| Computer Vision | OpenCV, DINOv2 Vision Transformer |
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

The following models were trained and compared using standard classification metrics:

| Metric | Custom CNN | DenseNet | DINOv2 + AB-MIL |
|---|---|---|---|
| Accuracy | — | — | **—** |
| Precision | — | — | **—** |
| Recall | — | — | **—** |
| F1-Score | — | — | **—** |

> 📌 Fill in your results after training. The proposed DINOv2 + AB-MIL framework demonstrated improved feature representation, classification performance, and interpretability compared to CNN-based approaches.

---

## 🔍 Interpretability

Attention heatmaps are generated to visualize the image regions most contributing to the final prediction. This provides clinically meaningful transparency into the model's decision-making process.

---

## 🔭 Future Work

- [ ] Training on larger and more diverse medical imaging datasets
- [ ] Explainable AI improvements for stronger clinical trust
- [ ] Multi-modal medical diagnosis systems
- [ ] Clinical validation and real-world deployment
- [ ] Integration with DICOM imaging workflows

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

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- [DINOv2](https://github.com/facebookresearch/dinov2) by Meta AI Research
- Publicly available knee X-ray imaging datasets
- Attention-Based Deep Multiple Instance Learning (Ilse et al., 2018)
