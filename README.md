# Deep Learning Framework for Scoliosis Detection and Severity Classification

## Mask R-CNN (ResNet50-FPN) Vertebra Segmentation with Geometric Cobb Angle Estimation on the Spinal-AI2024 Dataset

### Master's Thesis Project

This repository contains a deep learning framework for automated scoliosis assessment from spinal X-ray images.

The proposed approach combines:

- Vertebra instance segmentation using **Mask R-CNN (ResNet50-FPN)**
- Geometric **Cobb angle estimation**
- Automatic **scoliosis severity classification**

The framework was developed as part of a Master's thesis at **Mouloud Mammeri University of Tizi-Ouzou (UMMTO)**.

---

## Project Pipeline

```text
Spinal X-ray
      │
      ▼
Mask R-CNN (ResNet50-FPN)
      │
      ▼
Vertebra Segmentation
      │
      ▼
Cobb Angle Estimation
      │
      ▼
Severity Classification
```

---

## Dataset

This project uses the **Spinal-AI2024** dataset, which provides spinal radiographs along with vertebral segmentation annotations and Cobb angle measurements.

---

## Technologies

- Python
- PyTorch
- TorchVision
- OpenCV
- Albumentations
- NumPy
- Scikit-learn
- Google Colab

---

## Repository Structure

```text
.
├── notebooks/
├── models/
├── training/
├── inference/
├── results/
├── README.md
```

---

## Authors

- **Manel Hamdaoui**
- **Malha-Thilleli Arab**

### Supervisor

- **Dr. Nadhir Nouioua**

---

## Citation

If you use this work, please cite:

```bibtex
@mastersthesis{hamdaouiarab026,
  author = {Hamdaoui, Manel and Arab, Malha-Thilleli},
  title = {Deep Learning Framework for Scoliosis Detection and Severity Classification},
  school = {Mouloud Mammeri University of Tizi-Ouzou , Algeria},
  year = {2026}
}
`
