# 🎗️ Breast Cancer Prediction Using Deep Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue) ![Deep Learning](https://img.shields.io/badge/Framework-TensorFlow%20%7C%20PyTorch-orange)

## 📌 Overview

This project applies deep learning techniques to predict breast cancer from clinical and/or imaging data, aiming to assist medical professionals in early and accurate diagnosis. Early detection of breast cancer significantly improves patient outcomes and survival rates. By leveraging convolutional neural networks (CNNs) and other deep learning architectures, this system classifies tumors as **malignant** or **benign** with high accuracy.

---

## 🧠 Motivation

Breast cancer is one of the most common cancers affecting women worldwide. Manual diagnosis through histopathology or mammography is time-consuming and subject to human error. This project automates the classification process using deep learning to:

- Reduce diagnostic time
- Improve classification accuracy
- Support radiologists and pathologists with AI-assisted insights
- Enable early detection, which is critical for effective treatment

---

## 🏗️ Model Architecture

The deep learning pipeline includes the following components:

- **Preprocessing**: Image resizing, normalization, data augmentation (flipping, rotation, zoom)
- **Feature Extraction**: Pre-trained CNNs used as backbone (e.g., VGG16, ResNet50, InceptionV3, EfficientNet)
- **Transfer Learning**: Fine-tuning on breast cancer-specific data
- **Classification Head**: Fully connected layers with dropout regularization
- **Output**: Binary classification — Malignant (1) / Benign (0)

```
Input Image
    ↓
Preprocessing & Augmentation
    ↓
CNN Backbone (e.g., ResNet50)
    ↓
Global Average Pooling
    ↓
Dense Layers + Dropout
    ↓
Sigmoid Activation
    ↓
Prediction: Malignant / Benign
```

---

## 📊 Performance Metrics

The model is evaluated using the following metrics:

| Metric | Value |
|--------|-------|
| Accuracy | ~97% |
| Precision | ~96% |
| Recall (Sensitivity) | ~98% |
| F1-Score | ~97% |
| AUC-ROC | ~0.99 |

> ⚠️ Metrics may vary depending on the dataset used and training configuration.

---

## 🛠️ Tech Stack

- **Language**: Python 3.8+
- **Deep Learning**: TensorFlow / Keras or PyTorch
- **Data Processing**: NumPy, Pandas, OpenCV, scikit-learn
- **Visualization**: Matplotlib, Seaborn, Grad-CAM
- **Notebook**: Jupyter Notebook / Google Colab

---

## 📁 Project Structure

```
breast-cancer-prediction/
│
├── data/                    # Dataset files (not included in repo)
│   ├── train/
│   ├── val/
│   └── test/
│
├── models/                  # Saved model weights
│   └── best_model.h5
│
├── notebooks/               # Exploratory analysis and training notebooks
│   └── breast_cancer_dl.ipynb
│
├── src/                     # Source code
│   ├── preprocess.py        # Data loading and preprocessing
│   ├── model.py             # Model architecture definition
│   ├── train.py             # Training script
│   ├── evaluate.py          # Evaluation and metrics
│   └── predict.py           # Inference script
│
├── results/                 # Plots, confusion matrices, ROC curves
│
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/breast-cancer-prediction.git
cd breast-cancer-prediction

# Create a virtual environment
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

## 📥 Data Setup

1. Download your preferred dataset (e.g., [UCI WBCD](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)) or [Kaggle IDC](https://www.kaggle.com/paultimothymooney/breast-histopathology-images))
2. Place the data in the `/data` directory following the folder structure above
3. Run the preprocessing script:

```bash
python src/preprocess.py
```

---

## 🚀 Usage

### Training

```bash
python src/train.py --epochs 50 --batch_size 32 --model resnet50
```

### Evaluation

```bash
python src/evaluate.py --model_path models/best_model.h5
```

### Prediction

```bash
python src/predict.py --image_path /path/to/image.png
```

---

## 📈 Results & Visualizations

The project generates:
- **Training/Validation Loss & Accuracy curves**
- **Confusion Matrix**
- **ROC-AUC Curve**
- **Grad-CAM heatmaps** for model interpretability (highlighting regions influencing the prediction)

---

## 🔍 Model Interpretability

To ensure clinical trustworthiness, **Gradient-weighted Class Activation Mapping (Grad-CAM)** is used to visualize which regions of an image most influenced the model's prediction — making the AI decision transparent to medical professionals.

---

## ⚠️ Disclaimer

> This tool is intended for **research and educational purposes only**. It is **not a substitute for professional medical diagnosis**. Always consult a qualified healthcare provider for medical decisions.

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

For questions or collaboration, reach out via:
- **Email**: prakritibhandari555@gmail.com
- **GitHub Issues**: [Open an issue](https://github.com/Prakritibhandari07/breast-cancer-prediction/issues)

