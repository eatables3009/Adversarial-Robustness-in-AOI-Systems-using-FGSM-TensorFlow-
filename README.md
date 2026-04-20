# Adversarial Robustness in AOI Systems

## 📌 Overview
This project demonstrates how **Automated Optical Inspection (AOI) systems** can be compromised using **adversarial attacks**.  
A deep learning model trained for pattern classification is attacked using **Fast Gradient Sign Method (FGSM)**, reducing accuracy drastically despite no visible change in input images.

---

## 🎯 Problem Statement
Modern inspection systems achieve high accuracy but are vulnerable to **adversarial noise**, which can:
- Cause **incorrect classification**
- Hide critical defects
- Reduce system reliability without visible changes

---

## 🧠 Methodology

### Dataset
- **Fashion-MNIST** used as a proxy for structural pattern classification

### Model
- CNN with:
  - Conv2D + ReLU
  - MaxPooling
  - Dense layers

### Attack
- **FGSM (Fast Gradient Sign Method)**
- Perturbation level: **ε = 0.05**

### Defense
- **Adversarial Training**
- Retraining model on adversarial samples

---

## ⚙️ Workflow

1. Data preprocessing (normalization + reshaping)
2. Train baseline CNN model
3. Generate adversarial examples using FGSM
4. Evaluate model performance (clean vs attacked)
5. Retrain model with adversarial data
6. Compare robustness improvement

---

## 📊 Results

### Performance Drop (Under Attack)
- Accuracy: **91% → 27%**
- Precision: **91.66% → 30.65%**
- Recall: **91.52% → 27.81%**
- F1 Score: **91.54% → 28.21%**

### ROC Analysis
- Clean System: **AUC ≈ 0.99**
- Attacked System: **AUC ≈ 0.86**

---

## 🔍 Key Insights
- Small perturbations can **break model reliability**
- Model retains features (AUC high) but **fails decision-making**
- Adversarial noise causes **confident misclassification**

---

## 🛡️ Defense Results
- Adversarial training improves robustness significantly
- Model becomes more resistant to FGSM attacks

---

## 📈 Visualizations
- Clean vs adversarial image comparison
- ROC curves
- Performance metrics table

---

## 🧪 Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Scikit-learn

---

## 🏁 Conclusion

This project highlights a critical limitation of AI systems:  

**high accuracy does not guarantee robustness**, especially in safety-critical inspection systems.
