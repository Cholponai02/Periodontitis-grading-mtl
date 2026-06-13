# Topologically-Constrained Multi-Task Learning for Periodontitis Grading

## 🦷 Project Overview

This project investigates automated periodontitis grading from intra-oral dental radiographs using a Multi-Task Learning (MTL) framework.

The proposed approach jointly performs:

* Radiograph-wise segmentation
* Periodontitis grade classification

A clinically motivated Anatomical Consistency Loss is introduced to encourage consistency between the predicted disease grade and the CEJ–Bone anatomical distance extracted from the dataset annotations.

In addition, Grad-CAM visualization is used to improve model interpretability and verify whether the network focuses on clinically relevant anatomical regions.

---

## 🎯 Main Objectives

* Develop a multi-task deep learning model for simultaneous segmentation and grading.
* Generate weak grading labels from CEJ–Bone anatomical distance.
* Introduce an Anatomical Consistency Loss as a clinically motivated constraint.
* Compare the proposed model against a baseline model through an ablation study.
* Analyze model behavior using Grad-CAM visualizations.

---

## 📊 Dataset

This project uses the DenPAR (Dental Periodontal Radiograph) Dataset.

Dataset split:

* Training: 650 samples
* Validation: 150 samples
* Testing: 200 samples

Available annotations:

* Radiograph-wise segmentation masks
* Tooth-wise segmentation masks
* CEJ keypoints
* Bone-level annotations

### Dataset Source

The dataset used in this project can be downloaded from:

[https://drive.google.com/.....](https://drive.google.com/file/d/1GgFY8Haww2sRpR9_EMLVOzZCLlCOjBrg/view?usp=sharing)

After downloading, extract the archive into:

```text
CompVision_Project-3/
├── Training/
├── Validation/
├── Testing/
└── Characteristics of radiographs included.xlsx
```

---

## 🛠 Tech Stack

* Python
* PyTorch
* Google Colab
* NVIDIA T4 GPU
* NumPy
* Pandas
* Matplotlib
* OpenCV

---

## 🧠 Model Architecture

The proposed architecture is a Multi-Task U-Net consisting of:

* Shared convolutional encoder
* Segmentation decoder
* Classification head

The segmentation branch predicts radiograph-wise masks, while the classification branch predicts periodontitis grades.

### Proposed Extension

An Anatomical Consistency Loss is added to enforce agreement between:

* Predicted disease grade
* CEJ–Bone anatomical distance

This encourages anatomically meaningful predictions.

---

## 🔬 Experimental Setup

Framework: PyTorch

Hardware:

* Google Colab
* NVIDIA T4 GPU

Training Configuration:

* Image Size: 256 × 256
* Batch Size: 2
* Learning Rate: 0.0001
* Epochs: 4

---

## 📈 Results

### Baseline Model

* Validation Accuracy: 74.0%
* Dice Score: 0.906
* IoU: 0.840

### Proposed Model (Anatomical Constraint)

* Validation Accuracy: 70.0%
* Dice Score: 0.895
* IoU: 0.823

### Interpretation

The proposed anatomical constraint did not improve overall performance on the current dataset.

A possible explanation is that grading labels were already generated from CEJ–Bone distance measurements, making the additional anatomical constraint partially redundant.

Nevertheless, the study demonstrates the feasibility of integrating clinically motivated constraints into a multi-task learning framework.

---

## 🔍 Model Evaluation

The following evaluation techniques were used:

* Validation Accuracy
* Dice Score
* Intersection over Union (IoU)
* Confusion Matrix
* Ablation Study
* Qualitative Segmentation Visualization
* Training Curves
* Grad-CAM Analysis

---

## 📂 Project Structure

```text
1. Imports
2. Globals
3. Utils
4. Data Exploration
5. Data
6. DataLoader
7. Data Analysis
8. Network
9. Train
10. Baseline Training
11. Proposed Method
12. Proposed Model Training
13. Evaluation
14. Ablation Study
15. Qualitative Visualization
16. Training Curves
17. Grad-CAM Visualization
```

---

## 🚀 How to Run

1. Mount Google Drive in Google Colab.
2. Download and place the DenPAR dataset in:

```text
/content/drive/MyDrive/Colab_Notebooks/CompVision_Project-3/
```

3. Enable GPU acceleration:

```text
Runtime → Change Runtime Type → GPU
```

4. Run notebook cells sequentially.

---

## ⚠️ Limitations

* Highly imbalanced dataset
* Weak labels generated automatically from anatomical measurements
* Limited training time due to computational constraints
* Clinical grades are not expert-annotated

---

## 🔮 Future Work

* Improved class balancing techniques
* Longer training schedules
* Expert-annotated clinical grades
* Stronger anatomical constraints
* More advanced explainability methods

---

## 📚 References

1. DenPAR Dataset
2. Ronneberger et al., U-Net: Convolutional Networks for Biomedical Image Segmentation (2015)
3. PyTorch Documentation
4. Computer Vision Course Material (Sapienza University of Rome)

---

## 👩‍💻 Author

**Cholponai Manapova**

Computer Vision (A.Y. 2025–2026)

Sapienza University of Rome
