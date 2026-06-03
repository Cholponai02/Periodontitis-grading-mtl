# Topologically-Constrained Multi-Task Learning for Periodontitis Grading

## 🦷 Project Overview

This project investigates automated periodontitis grading from intra-oral dental radiographs using a Multi-Task Learning framework.

The proposed approach jointly performs:

- Radiograph-wise segmentation
- Periodontitis grade classification

A novel Anatomical Consistency Loss is introduced to encourage consistency between the predicted grade and the clinically relevant CEJ–Bone distance extracted from annotations.

## 🎯 Main Objectives

- Develop a multi-task deep learning model for segmentation and grading.
- Generate weak grading labels from CEJ–Bone anatomical distance.
- Introduce an Anatomical Consistency Loss as a clinically motivated constraint.
- Compare the proposed method against a baseline model through an ablation study.

## 📊 Dataset

The project uses the DenPAR dataset.

Dataset split:

- Training: 650 samples
- Validation: 150 samples
- Testing: 200 samples

Available annotations:

- Radiograph-wise segmentation masks
- Tooth-wise segmentation masks
- CEJ keypoints
- Bone-level annotations

## 🛠 Tech Stack

- Python
- PyTorch
- Google Colab (T4 GPU)
- NumPy
- Pandas
- Matplotlib
- 
## 🧠 Model Architecture

The proposed architecture is a Multi-Task U-Net consisting of:

- Shared convolutional encoder
- Segmentation decoder
- Classification head

The classification branch predicts periodontitis grade, while the segmentation branch predicts radiograph-wise masks.

## 📈 Results

### Baseline

- Validation Accuracy: 71.3%
- Dice Score: 0.912
- IoU: 0.847

### Proposed Model

- Validation Accuracy: 70.7%
- Dice Score: 0.892
- IoU: 0.814

Although the proposed anatomical constraint did not improve overall performance, the study demonstrates the feasibility of integrating clinically motivated constraints into a multi-task learning framework.

## 📂 Project Structure
Following the structure required by Prof. Irene Amerini:
*   `Imports`: Package management.
*   `Globals`: Hyperparameters and paths.
*   `Utils`: Visualization and helper functions.
*   `Data`: Custom PyTorch Dataset for DenPAR (COCO format).
*   `Network`: Mask R-CNN implementation.
*   `Train`: Training loops and multi-task loss functions.
*   `Evaluation`: Metrics, Ablation Study, and Grad-CAM analysis.

## 🚀 How to Run
1.  Mount your Google Drive in Colab.
2.  Ensure the dataset is located at `/Colab_Notebooks/CompVision_Project-3/`.
3.  Run the notebook cells sequentially.

## 👩‍💻 Author
*   **Name:** Cholponai Manapova
*   **Course:** Computer Vision (A.Y. 2025-2026), Sapienza University of Rome
