# Deep Learning-Based Classification of Paper-Based Microscopic Images

This project explores the use of **Convolutional Neural Networks (CNNs)** to classify **paper-based microscopic images** into **NonCancer**, **Medium**, and **Cancer** categories. The work was completed as part of an internship at **Indian Institute of Information Technology, Design and Manufacturing (IIITDM) Kancheepuram**.

---

## 📌 Project Overview

* **Objective**: To evaluate whether CNNs can detect patterns in inexpensive, scanned/printed histopathology slides for preliminary cancer screening.
* **Key Idea**: Utilize **color and texture features** in low-cost images to perform classification.
* **Scope**:

  * Preprocessing microscopic images using OpenCV.
  * Training a CNN on labeled images.
  * Mapping predictions into 3 categories (`NonCancer`, `Medium`, `Cancer`).
  * Evaluating accuracy and identifying challenges like overfitting.

---

## 🧩 Dataset

* Images of tissue samples scanned/printed on paper.
* Resized to **128×128 pixels**.
* Normalized by dividing pixel values by 255.
* Retained RGB channels to capture **color + texture features**.

---

## 🏗️ Model Architecture

The CNN model includes:

* **Conv Layer 1**: 32 filters, ReLU activation
* **MaxPooling Layer 1**
* **Conv Layer 2**: 64 filters, ReLU activation
* **MaxPooling Layer 2**
* **Flatten Layer**
* **Dense Layer (Fully Connected)**
* **Dropout Layer (50%)**
* **Output Layer**: Sigmoid (binary classification mapped into 3 categories)

---

## ⚙️ Training Strategy

* **Epochs**: 15
* **Loss Function**: Binary Cross-Entropy
* **Evaluation Metric**: Accuracy
* **Validation Split**: 10%
* Predictions mapped as:

  * `NonCancer` → Probability < 0.5
  * `Medium` → 0.5 ≤ Probability ≤ 0.8
  * `Cancer` → Probability > 0.8

---

## 📊 Results

* **Overall Accuracy**: ~60–65%
* **NonCancer Accuracy**: 80–100%
* **Cancer Accuracy**: 70–100%
* **Medium Accuracy**: Lower (due to imbalance & fewer samples)

> ⚠️ **Note:** Validation accuracy was significantly lower than training accuracy, indicating **overfitting**.

---

## 🚧 Challenges & Future Work

* **Challenges**: Small dataset, class imbalance, low-resolution images, and label noise.
* **Future Improvements**:

  * Increase dataset size
  * Apply data augmentation
  * Use pre-trained CNN architectures (e.g., ResNet, VGG16)
  * Apply stain normalization for histopathology

---

## 🛠️ Installation & Usage

Clone the repository and install dependencies:

```bash
git clone https://github.com/<your-username>/oral-cancer-ml.git
cd oral-cancer-ml
pip install -r requirements.txt
```

Run the Jupyter Notebook:

```bash
jupyter notebook oralcancerml.ipynb
```

---

## 📖 Reference

This project is based on the report:
*Gali Satya Priya, "Deep Learning-Based Classification of Paper-Based Microscopic Images," IIITDM Kancheepuram, 2025.*

Related paper: [Paper-based Devices for Cancer Diagnostics](https://www.sciencedirect.com/science/article/pii/S2772906024005430)

---


**Gali Satya Priya**
B.Tech CSE | IIITDM Kancheepuram

---
