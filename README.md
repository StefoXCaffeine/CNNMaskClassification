 🎭 Mask Detection CNN

> Automatic face classification for mask detection using Convolutional Neural Networks

![Python](https://img.shields.io/badge/Python-3.10-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Accuracy](https://img.shields.io/badge/Accuracy-93%25-brightgreen)

---

## 📋 Overview

This project implements a **CNN** for detecting face mask status, automatically classifying into three categories:

| Class | Description |
|-------|-------------|
| 🟢 With Mask | Face with correctly worn mask |
| 🔴 Without Mask | Face without any mask |
| 🟡 Mask Worn Incorrectly | Mask worn in an incorrect manner |

---

## 🏗️ Project Architecture

RAW Dataset (Kaggle) │ ▼ ┌─────────────────┐ │ Parsing XML │ → Bounding box extraction │ Annotations │ └─────────────────┘ │ ▼ ┌─────────────────┐ │ Face Cropping │ → Resize to 64x64 │ & Resize │ └─────────────────┘ │ ▼ ┌─────────────────┐ │ Data │ → Rotation, Flip, Color │ Augmentation │ variations, Occlusions └─────────────────┘ │ ▼ ┌─────────────────────────────────────┐ │ CNN Model (TensorFlow) │ │ │ │ Conv2D(32) → MaxPool │ │ Conv2D(64) → MaxPool │ │ Conv2D(128) → MaxPool │ │ Dense(128) + Dropout │ │ Dense(3) + Softmax │ └─────────────────────────────────────┘ │ ▼ ┌─────────────────┐ │ Haar Cascade │ → Real-time detection │ + Webcam │ via webcam └─────────────────┘


---

## ⚙️ Tech Stack

| Category | Library |
|----------|---------|
| **Deep Learning** | TensorFlow / Keras |
| **Vision** | OpenCV, Albumentations |
| **ML Utilities** | Scikit-learn |
| **Data** | NumPy, Pandas |
| **Visualization** | Matplotlib, Seaborn |

---

## 📊 Results

| Metric | Value |
|--------|-------|
| **Test Accuracy** | 93% |
| **Precision (macro avg)** | 93% |
| **Recall (macro avg)** | 92% |

### Per-Class Performance

| Class | Precision | Recall | F1-Score |
|-------|-----------|--------|----------|
| With Mask | 94% | 95% | 95% |
| Without Mask | 93% | 95% | 94% |
| Mask Incorrect | 91% | 86% | 89% |

---

## 🚀 Setup

### 1. Clone the repository
```bash```
git clone https://github.com/username/mask-detection-cnn.git
cd mask-detection-cnn
2. Install dependencies
pip install -r requirements.txt
or manually:

pip install tensorflow opencv-python albumentations scikit-learn numpy pandas matplotlib seaborn
3. Dataset structure
maskDetection/
├── annotations/           # XML files with bounding boxes
├── images/               # Original images
├── with_mask/            # Faces with mask
├── without_mask/         # Faces without mask
└── mask_weared_incorrect/ # Incorrectly worn mask
4. Run the notebook
jupyter notebook maskdetection.ipynb
💡 Usage
Model Training
Run notebook cells in order:

Data loading and preprocessing
Data augmentation
CNN definition and training
Evaluation (confusion matrix, classification report)
Real-time Inference
# Webcam detection
camera = cv2.VideoCapture(0)
# ... (see notebook for full code)
📁 Main Files
File	Description
maskdetection.ipynb	Complete pipeline notebook
cnnMask.keras	Trained model
README.md	This documentation
🔮 Future Improvements
 Increase input resolution (128x128 or higher)
 Transfer learning with MobileNetV2/ResNet50
 BatchNormalization for more stable training
 Class weights for dataset balancing
 K-Fold Cross-Validation
📜 License
MIT License - see LICENSE file for details.

👤 Author
Your Name

GitHub: @username
LinkedIn: linkedin.com/in/username
⭐ If you find this project useful, leave a star!
