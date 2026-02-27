# Automated 3D CT Reconstruction and Lung Tumor Segmentation in TCGA-LUSC Using TotalSegmentator

## Overview

This project presents an end-to-end computational pipeline for processing thoracic CT scans from the TCGA-LUSC (The Cancer Genome Atlas – Lung Squamous Cell Carcinoma) dataset. The framework reconstructs volumetric CT data from raw DICOM files, performs intensity standardization in Hounsfield Units (HU), preserves anatomical voxel spacing, and applies automated multi-organ segmentation using TotalSegmentator.

The pipeline demonstrates practical implementation of medical image preprocessing, volumetric reconstruction, and AI-driven anatomical segmentation, forming a foundational step toward radiomics and quantitative imaging research.

---

## Scientific Motivation

Accurate 3D reconstruction and segmentation of lung CT scans are critical for:

- Radiomic feature extraction
- Tumor burden quantification
- Morphological analysis
- AI-based diagnostic modeling
- Precision oncology research

This project replicates a clinically relevant imaging workflow using open-source computational tools.

---

## Methodology

### DICOM Processing
- Recursive identification of DICOM slices
- Sorting by ImagePositionPatient (Z-axis)
- Extraction of pixel arrays
- Conversion to Hounsfield Units (HU)

### 3D Volume Reconstruction
- Stack slices into volumetric array
- Preserve anatomical spacing (z, y, x)
- Maintain physical voxel dimensions

### Visualization
- Lung windowing (-600 HU center, 1500 HU width)
- Interactive slice navigation
- Maximum Intensity Projection (MIP)

### NIfTI Conversion
- Convert NumPy volume → SimpleITK image
- Apply correct spatial metadata
- Export as `.nii.gz` for downstream processing

### Automated Segmentation
- Run TotalSegmentator
- Extract lung and tumor masks
- Overlay segmentation on CT slices

---

## Pipeline Architecture
Raw DICOM Files
↓
DICOM Parsing & Sorting
↓
HU Conversion
↓
3D Volume Reconstruction
↓
Voxel Spacing Preservation
↓
NIfTI Export (.nii.gz)
↓
TotalSegmentator
↓
Organ & Tumor Masks
↓
Segmentation Visualization


---

## Technologies Used

- Python 3.10+
- NumPy
- pydicom
- SimpleITK
- Matplotlib
- ipywidgets
- TotalSegmentator
- Google Colab

---

## Repository Structure
TCGA-LUSC-CT-Segmentation/
│
├── FJ_update.ipynb # Original Colab notebook
├── FJ_update.py # Script version
├── requirements.txt
└── README.md

## Dataset
Dataset not included due to size and TCGA data usage policies.
Users must download TCGA-LUSC dataset from TCIA portal.  
Dataset link:  https://www.cancerimagingarchive.net/collection/tcga-lusc/
