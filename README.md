# Brain MRI Tumor Segmentation with Deep Learning  

This project implements a **deep learning algorithm for automated brain tumor segmentation** using the **LGG Brain MRI Segmentation Dataset**. The algorithm is designed to identify and segment different tumor regions from MRI scans, enabling radiology research and potential clinical decision support.  

---

## 🎯 Project Goal  

To build a robust **segmentation pipeline** that:  
- Preprocesses Brain MRI volumes (skull stripping, normalization, resizing)  
- Trains a **deep convolutional neural network (CNN)** for multi-class tumor segmentation  
- Detects and classifies tumor subregions:  
  - Necrotic core  
  - Enhancing tumor  
  - Non-enhancing tumor core  
  - Edema  
- Evaluates performance against expert manual annotations  

---

## 📌 Dataset  

- **Source**: [The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/)  
- **Patients**: 110 cases from **The Cancer Genome Atlas (TCGA)** lower-grade glioma collection  
- **Modalities**: T1-weighted (T1w) and T2-weighted/FLAIR scans  
- **Format**: NIfTI volumes (`.nii`)  
- **Annotations**: Manual segmentation masks provided by expert radiologists  

---

## 🧭 Workflow  

### 1. **Data Preprocessing**  
- Load NIfTI volumes  
- Skull stripping (removal of non-brain tissue)  
- Intensity normalization  
- Patch extraction for model training  

### 2. **Model Architecture**  
- Implemented a **U-Net based CNN** tailored for 3D medical imaging  
- Encoder-decoder structure with skip connections  
- Supports multi-class segmentation of tumor regions  

### 3. **Training**  
- Loss function: Dice Loss + Cross Entropy  
- Optimizer: Adam  
- Data augmentation: rotations, flips, elastic deformations  

### 4. **Evaluation**  
- Metrics: Dice coefficient, Jaccard index, Precision/Recall  
- Comparison against manual radiologist annotations  

---

## 📂 Repository Structure  

- `data/` – MRI scans & segmentation masks (NIfTI format)  
- `preprocessing/` – Scripts for skull stripping, normalization, patch generation  
- `models/` – U-Net implementation and training scripts  
- `notebooks/` – Jupyter notebooks for EDA and experiments  
- `results/` – Saved model checkpoints and performance reports  

---

## 🚀 How to Run  

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/brain-mri-segmentation.git
   cd brain-mri-segmentation
