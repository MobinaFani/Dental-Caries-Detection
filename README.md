# 🦷 Dental Caries Detection using Deep Learning

A deep learning project for binary classification of dental images to detect caries (tooth decay).  
Developed in **Google Colab** using **Transfer Learning (VGG16)** and **TensorFlow/Keras**.

---

## 📌 Project Overview

This project uses a pre-trained **VGG16** model (with ImageNet weights) and fine-tunes it to classify dental images as either **Caries (decayed)** or **Healthy**.  
The model is trained on a custom dataset stored in **Google Drive**.

---

## 🧠 Model Architecture

- **Base model**: VGG16 (`include_top=False`, `pooling='max'`)
- **Custom layers**:
  - Dropout
  - Dense (1024 units, `elu`)
  - Dense (2048 units, L1 regularization, `elu`)
  - Final Dense (1 unit, `sigmoid`)
- **Loss function**: Binary Crossentropy
- **Optimizer**: Adam
- **Metrics**: Accuracy

⚠️ The VGG16 base is frozen during training to leverage pre-learned features.

---
## 📁 Dataset

The dataset used for training and testing is stored in Google Drive:

👉 [Click here to view/download the dataset](https://drive.google.com/drive/folders/1is5LAMJVoyQ_DFK_OoYdt3n6CNdxJhj-)

Make sure you mount your Google Drive in Google Colab before accessing the dataset:

```python
from google.colab import drive
drive.mount('/content/drive')

🧪 Dataset Structure

The dataset should be organized like this:

Dental_dir/
│
├── Train_dir/
│   ├── Healthy/
│   └── Caries/
│
├── Test_dir/
│   ├── Healthy/
│   └── Caries/
│
└── Validation_dir/
    ├── Healthy/
    └── Caries/

🖼️ Images will be automatically resized to 230x230 during preprocessing.

📊 Training & Validation
	•	Epochs: 24
	•	Batch size: 20
	•	Data augmentation: rotation, zoom, shift, shear
	•	Accuracy and loss are plotted after training using matplotlib

🚀 How to Run

This project is designed to run in Google Colab.

Steps:
	1.	Mount your Google Drive:

from google.colab import drive
drive.mount('/content/drive')


	2.	Prepare your dataset in the correct directory format inside Drive.
	3.	Run all cells in the notebook.

📈 Sample Output

Training and validation accuracy/loss curves are shown after training.

👩🏻‍💻 Author

Mobina Fani
Python & Deep Learning Enthusiast 💻
🌱 Learning with passion | Dreaming big

🗂 Notes
	•	Make sure you have access to your dataset on Google Drive.
	•	Requires: TensorFlow, Keras, matplotlib, and Google Colab environment.

📎 License

This project is released for educational and academic use only.



