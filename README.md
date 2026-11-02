# Scoliosis Severity Assessment from Spinal X-rays: Mask R-CNN Vertebra Segmentation and Geometric Cobb Angle Estimation

## Master's Thesis Project

This repository contains research software developed as part of a Master's
thesis at Mouloud Mammeri University of Tizi Ouzou, Algeria.

The project investigates an automated pipeline for scoliosis assessment
from spinal X-ray images using vertebra instance segmentation, geometric
Cobb angle estimation, and angle-based severity classification.

## Overview

The pipeline combines three main stages:

1. Vertebra instance segmentation using Mask R-CNN with a ResNet50-FPN backbone.
2. Geometric Cobb angle estimation from the predicted vertebral masks.
3. Scoliosis severity classification based on the estimated angle.

Mask R-CNN is used for vertebra segmentation. Cobb angle estimation is
performed by geometric post-processing, rather than direct prediction by
the neural network. Severity classification is then obtained by applying
angle-based thresholds.

## Project Pipeline

```text
Spinal X-ray
      │
      ▼
Mask R-CNN (ResNet50-FPN)
      │
      ▼
Vertebra Instance Segmentation
      │
      ▼
Geometric Processing of Vertebral Masks
      │
      ▼
Cobb Angle Estimation
      │
      ▼
Angle-Based Severity Classification
```

## Objectives

- Segment individual vertebrae in spinal X-ray images.
- Extract geometric information from the predicted masks.
- Estimate the Cobb angle.
- Assign a scoliosis severity category based on the estimated angle.
- Provide the implementation and documentation for academic research reuse.

## Dataset

The project uses the Spinal-AI2024 dataset, which includes spinal images,
vertebral segmentation annotations, and reference Cobb angle measurements.

Original dataset repository:
https://github.com/Ernestchenchen/Spinal-AI2024

The dataset is not redistributed in this repository. Users must consult
the original dataset repository for access instructions, licensing terms,
and citation requirements.

## Methods

### Vertebra Segmentation

The notebook uses a Mask R-CNN model with a ResNet50-FPN backbone,
initialized with pretrained weights and adapted for vertebra instance
segmentation.

### Geometric Cobb Angle Estimation

The predicted masks are processed to estimate vertebral geometry.
The implementation uses oriented rectangles to approximate vertebral
endplate directions and calculates an angle from selected vertebrae.

This is a geometric approximation derived from segmentation masks,
not a direct neural-network regression of the Cobb angle.

### Severity Classification

The estimated Cobb angle is passed to an angle-based classification
function. The implementation includes the severity labels Mild,
Moderate, and Severe.

The precise thresholds and handling of unclassified cases are defined
in the notebook.

## Technologies

- Python
- PyTorch
- TorchVision
- OpenCV
- Albumentations
- NumPy
- Pandas
- SciPy
- Scikit-learn
- Matplotlib
- pycocotools
- tqdm
- Google Colab

## Repository Structure

```text
automated-scoliosis-detection-classification/
├── automated_scoliosis_detection_classification.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
└── CITATION.cff
```

- `automated_scoliosis_detection_classification.ipynb`:
  main notebook containing data preparation, model training,
  geometric processing, and evaluation.
- `requirements.txt`: list of Python dependencies.
- `.gitignore`: exclusion rules for temporary files, model weights,
  and downloaded data.
- `LICENSE`: MIT license text.
- `CITATION.cff`: software citation metadata.

## Getting Started with Google Colab

### 1. Open the Notebook

Download `automated_scoliosis_detection_classification.ipynb` from this
repository and upload it to Google Colab.

### 2. Select a Runtime

Select a GPU runtime for model training and evaluation.

### 3. Review the Configuration

Before executing the notebook:

- Check the dataset download and extraction cells.
- Review the dataset directory paths.
- Update the Google Drive checkpoint directory for your own account.
- Review cells that delete or recreate local folders.
- Decide whether to train from the beginning or resume from an
  existing checkpoint.

The original notebook uses Colab-specific paths and Google Drive
integration. These paths may require changes in another environment.

### 4. Run the Cells

Run the notebook cells in order, following their dependencies:

1. Environment setup and imports.
2. Dataset preparation.
3. Data augmentation and data loaders.
4. Model initialization.
5. Training or checkpoint loading.
6. Segmentation inference.
7. Geometric Cobb angle estimation.
8. Severity classification and evaluation.

The repository does not include trained model weights or the dataset.

## Dependencies and Reproducibility

The Python libraries are listed in `requirements.txt`.

This file currently lists package names without fixed versions.
It should not be interpreted as a fully tested, version-locked
environment.

For reproducing the experiments, also consider the runtime,
GPU availability, package versions, dataset split, random seed,
and checkpoint used.

## Evaluation

The notebook includes evaluation procedures for:

- Vertebra segmentation.
- Cobb angle estimation.
- Angle-based severity classification.

The evaluation populations are not necessarily identical across tasks.
In particular, the three-class severity evaluation uses a filtered
subset rather than all test images.

Separate result files and figures are not included in this repository.

## Limitations and Research Use

This repository provides a research implementation associated with
a Master's thesis.

The geometric angle estimation depends on the quality of the predicted
vertebral masks. Classification results also depend on the angle
thresholds and the handling of cases outside the evaluated categories.

The software is intended for academic research and is not intended
to replace clinical assessment or support unsupervised medical decisions.

## Future Work

- Improve notebook organization and configuration.
- Extract reusable functions into Python modules.
- Document and test a version-locked execution environment.
- Investigate improvements to vertebral geometry estimation.
- Evaluate generalization on additional datasets.

## Authors

- ARAB Malha-Thilelli
- HAMDAOUI Manel

Mouloud Mammeri University of Tizi Ouzou, Algeria.

## Supervisor

Dr. Nadhir NOUIOUA

## Acknowledgments

We sincerely thank Dr. Nadhir NOUIOUA for his supervision,
scientific guidance, and support throughout this Master's thesis project.

## Citation

If you use this software in your research, please cite it using
the metadata provided in `CITATION.cff`.

The software citation title is:

Scoliosis Severity Assessment from Spinal X-rays: Mask R-CNN Vertebra
Segmentation and Geometric Cobb Angle Estimation

The citation refers to the software associated with the Master's thesis.
A separate bibliographic reference to the thesis may be added once its
official title and defense year have been confirmed.

## License

The project code is distributed under the MIT License.
See `LICENSE` for the full text.

Third-party code, libraries, datasets, and pretrained weights remain
subject to their respective licenses and terms.
