# Topologically-Constrained Multi-Task Learning for Periodontitis Grading

## 🦷 Project Overview
This project addresses the challenge of automated **Periodontal Bone Loss (PBL) grading** using deep learning. Unlike standard classification models, this approach utilizes **Multi-Task Learning (MTL)** to simultaneously perform semantic segmentation of dental structures and classification of periodontitis stages (Stage I-IV and Healthy).

The core objective is to ensure that the AI follows clinical logic by enforcing anatomical consistency between the **Cementoenamel Junction (CEJ)** and the **Alveolar Bone Crest (ABC)**[cite: 1].

## 🎯 Main Objectives
*   **Baseline Implementation:** Developing a dual-branch architecture for simultaneous segmentation and classification[cite: 1].
*   **Anatomical Constraints:** Integrating a methodological novelty (e.g., Distance-Map Loss) to penalize anatomically inconsistent predictions[cite: 1].
*   **Interpretability:** Using **Grad-CAM** to verify that the model focuses on relevant clinical landmarks rather than background noise[cite: 1].

## 📊 Dataset
The project utilizes the **DenPAR Dataset**, consisting of Intra-Oral Periapical Radiographs with:
*   **Images:** 1.3k+ training X-rays[cite: 1].
*   **Annotations:** COCO format instance segmentation masks and clinical grading[cite: 1].
*   **Metadata:** Arch (Upper/Lower) and FDI notation for specific teeth identification.

## 🛠 Tech Stack
*   **Language:** Python
*   **Framework:** PyTorch (Strictly following course requirements)
*   **Model Architecture:** Mask R-CNN with a ResNet-50-FPN backbone[cite: 1].
*   **Environment:** Google Colab with GPU acceleration.

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
*   **Student ID:** 2229146
*   **Course:** Computer Vision (A.Y. 2025-2026), Sapienza University of Rome
