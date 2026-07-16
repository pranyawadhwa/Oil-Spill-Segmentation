# Boundary-Aware Attention U-Net with Explainability for Oil Spill Segmentation in UAV RGB Imagery

## Overview

This repository presents a deep learning framework for semantic segmentation of oil spills in UAV RGB imagery. The work investigates the impact of attention mechanisms, boundary-aware optimization, and explainability on segmentation performance.

Three models are implemented and evaluated:

- **Model A:** U-Net + EfficientNet-B4 (Baseline)
- **Model B:** Attention U-Net + EfficientNet-B4
- **Model C (Proposed):** Attention U-Net + EfficientNet-B4 + Boundary IoU Loss + Focal Loss + Exponential Moving Average (EMA) + Grad-CAM Explainability

---

## Research Objective

The objective of this work is to improve segmentation of thin and irregular oil spill boundaries while maintaining high segmentation accuracy and providing interpretable model predictions through Grad-CAM visualizations.

---

## Dataset

**Zenodo Annotated RGB Oil Spill Dataset**

- UAV RGB Images
- CamVid segmentation format
- Train / Validation / Test split
- Image size: **512 × 512**

---

## Methodology

### Model A
- U-Net
- EfficientNet-B4 encoder
- Dice Loss + Binary Cross Entropy

### Model B
- Attention U-Net
- EfficientNet-B4 encoder
- Dice Loss + Focal Loss

### Model C (Proposed)
- Attention U-Net
- EfficientNet-B4 encoder
- Boundary IoU Loss
- Focal Loss
- EMA Weight Averaging
- Grad-CAM Explainability

---

# Test Set Results

| Model | IoU | Dice | Precision | Recall | F1 | Accuracy |
|------|------:|------:|------:|------:|------:|------:|
| Model A | 0.9019 | 0.9308 | **0.9701** | 0.9577 | **0.9638** | **0.9762** |
| Model B | 0.9116 | 0.9410 | 0.9588 | **0.9645** | 0.9617 | 0.9745 |
| **Model C (Proposed)** | **0.9157** | **0.9457** | 0.9575 | 0.9615 | 0.9595 | 0.9731 |

---

## Key Findings

- Proposed Model C achieved the highest **IoU** and **Dice Score**, indicating improved segmentation quality.
- Boundary-aware optimization improved localization of complex oil spill boundaries.
- Attention gates enhanced feature selection compared to the baseline model.
- Grad-CAM visualizations provide interpretable predictions by highlighting regions influencing model decisions.

---

## Repository Structure

```
Oil-Spill-Segmentation/

├── Notebooks/
│   ├── Notebook_1_Data_Pipeline.ipynb
│   ├── Notebook_2_Model_A_Baseline_UNet.ipynb
│   ├── Notebook_3_Model_B_Attention_UNet.ipynb
│   ├── Notebook_4_Model_C_BoundaryIoU_GradCAM.ipynb
│   └── Notebook_5_Final_Evaluation_Ablation.ipynb
│
├── Results/
│   ├── metrics/
│   ├── plots/
│   ├── gradcam/
│   └── final_results/
│
├── requirements.txt
└── README.md
```

---

## Technologies

- Python
- PyTorch
- Segmentation Models PyTorch (SMP)
- Albumentations
- OpenCV
- NumPy
- Scikit-learn
- Matplotlib
- Grad-CAM

---

## Future Work

- Multi-class marine pollution segmentation
- Transformer-based segmentation models
- Lightweight architectures for real-time UAV deployment
- Domain adaptation across different marine environments

---

## Authors

**Pranya Wadhwa**

Summer Research Internship Project
