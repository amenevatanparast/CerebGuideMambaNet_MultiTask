# CerebGuideMambaNet: Lightweight Multi-Task Learning for Fetal Cerebellar Segmentation and Dandy–Walker Malformation Classification

## Overview

CerebGuideMambaNet (DWMamba-KANet-Lite) is a lightweight multi-task deep learning framework designed for simultaneous fetal cerebellar segmentation and Dandy–Walker Malformation (DWM) classification from ultrasound images.

The framework integrates:

* Lightweight State-Space-Inspired (Lite-SSM) contextual modeling
* KAN-Inspired nonlinear feature transformation
* Prompt-Guided Feature Fusion (PGF)
* Boundary-Aware Segmentation Supervision
* Segmentation-Guided Classification (SGC)

Unlike conventional single-task approaches, the proposed architecture jointly learns anatomical localization and abnormality recognition within a unified network, improving feature sharing while maintaining low computational complexity.

---

## Architecture

The proposed framework consists of:

### Shared Encoder

* Lightweight convolutional stem
* Lite-SSM contextual modeling blocks
* KAN-inspired feature transformation modules

### Segmentation Decoder

* Prompt-guided skip fusion
* Progressive feature reconstruction
* Cerebellar segmentation output

### Boundary Branch

* Auxiliary edge prediction head
* Boundary-aware supervision

### Classification Branch

* Segmentation-guided feature extraction
* Morphology-aware descriptors
* DWM classification output

---

## Main Contributions

✔ Simultaneous cerebellar segmentation and DWM classification

✔ Lightweight architecture (~1.5M parameters)

✔ State-space-inspired contextual modeling

✔ KAN-inspired nonlinear feature learning

✔ Prompt-guided anatomical feature fusion

✔ Segmentation-guided morphology-aware classification

✔ Explainable predictions using Score-CAM visualization

---

## Dataset

The dataset consists of fetal brain ultrasound images containing:

* Normal fetal cerebellum
* Dandy–Walker Malformation (DWM)

### Dataset Statistics

| Class  | Samples |
| ------ | ------- |
| Normal | 200     |
| DWM    | 80      |
| Total  | 280     |

### Data Split

| Split      | Percentage |
| ---------- | ---------- |
| Training   | 70%        |
| Validation | 15%        |
| Testing    | 15%        |

All video-derived samples were grouped at the case level to prevent information leakage between subsets.

---

## Training Configuration

| Parameter           | Value              |
| ------------------- | ------------------ |
| Framework           | TensorFlow / Keras |
| Input Size          | 256×256×3          |
| Optimizer           | Adam               |
| Learning Rate       | 1e-4               |
| Batch Size          | 8                  |
| Epochs              | 80                 |
| Segmentation Loss   | BCE + Dice         |
| Classification Loss | Focal Loss         |
| Edge Loss           | BCE + Dice         |

### Data Augmentation

* Horizontal flip
* Vertical flip
* Random rotation
* Random zoom
* Brightness adjustment
* Contrast adjustment

---

## Results

### Segmentation Performance

| Metric  | Value  |
| ------- | ------ |
| Dice    | 88.74% |
| Jaccard | 80.71% |

### Classification Performance

| Metric    | Value   |
| --------- | ------- |
| Accuracy  | 100.00% |
| Precision | 100.00% |
| Recall    | 100.00% |

---

## BRISC2025 Cross-Domain Evaluation

To evaluate architectural adaptability, the framework was retrained and tested on the public BRISC2025 brain tumor MRI dataset.

### BRISC2025 Results

| Metric    | Value  |
| --------- | ------ |
| Dice      | 82.17% |
| Jaccard   | 70.92% |
| Accuracy  | 96.93% |
| Precision | 95.80% |
| Recall    | 95.72% |
| F1-score  | 95.76% |

These results demonstrate that the architecture remains effective beyond fetal ultrasound imaging after task-specific retraining.

---

## Repository Structure

```text
├── notebooks/
│   └── CerebLite_MTLNet.ipynb
│
├── models/
│   └── saved_models/
│
├── figures/
│   ├── architecture.png
│   ├── segmentation_examples.png
│   └── scorecam_examples.png
│
├── dataset/
│   ├── images/
│   ├── masks/
│   └── labels.csv
│
└── README.md
```

---

## Running the Notebook

### Clone Repository

```bash
git clone https://github.com/yourusername/CerebGuideMambaNet.git
cd CerebGuideMambaNet
```

### Install Requirements

```bash
pip install tensorflow
pip install numpy
pip install opencv-python
pip install scikit-learn
pip install matplotlib
pip install albumentations
```

### Run

Open:

```text
CerebLite_MTLNet.ipynb
```

using:

* Google Colab
* Jupyter Notebook
* JupyterLab

---

## Citation

If you use this work in your research, please cite:

```bibtex
@article{Vatanparast2026CerebGuideMambaNet,
  title={CerebGuideMambaNet: A Lightweight Multi-Task Framework for Simultaneous Fetal Cerebellar Segmentation and Dandy–Walker Malformation Classification},
  author={Vatanparast, Amene and Fateh, Mansoor and Mashayekhi, Hoda and Ferdowsi, Saideh},
  journal={Under Review},
  year={2026}
}
```

---

## Acknowledgements

This work was conducted at:

* Shahrood University of Technology
* University of Essex

The authors gratefully acknowledge all publicly available fetal ultrasound resources and the BRISC2025 dataset contributors.

---

## License

This repository is released for academic and research purposes.

Please contact the authors for commercial usage permissions.
