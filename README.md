# SAM-MaGuP: Mamba Guided Boundary Prior for Generalized Polyp Segmentation

## Overview
Polyp segmentation is a critical task for early detection of colorectal cancer, but challenges like weak or blurry boundaries make it a demanding problem. SAM-MaGuP introduces a novel approach to robust polyp segmentation by enhancing the **Segment Anything Model (SAM)** with boundary-focused innovations.  

**Key Features:**
- Incorporates a **Boundary Distillation Component (BDC)** to refine weak boundary details.
- Leverages a unique **1D-2D Mamba adapter** for multi-scale feature fusion.
- Achieves state-of-the-art results across five diverse benchmark datasets.

![Framework](path/to/your/image.png)

---

## Highlights
- **Boundary Distillation:** Sharpens model focus on ambiguous or weakly defined regions.
- **1D-2D Mamba Adapter:** Captures long-range dependencies across spatial and channel dimensions.
- **Multi-Scale Refinement:** Enhances SAM’s feature representation for improved accuracy.
- **Robust Performance:** Outperforms existing methods on seen and unseen datasets with unmatched segmentation precision.

---

## Architecture
SAM-MaGuP consists of:
1. **MaGuP Module:** A plug-in adapter for SAM, combining:
   - **Multi-scale Spatial Decomposition (MSD):** Extracts coarse-to-fine polyp features.
   - **Boundary Distillation Component (BDC):** Refines polyp boundaries using cross-attention mechanisms.
2. **SAM Backbone:** Augmented with domain-specific knowledge for medical image segmentation.

---

## Results
### Quantitative Metrics
SAM-MaGuP sets a new benchmark in segmentation accuracy across datasets like Kvasir-SEG, ETIS, and ClinicDB. It consistently achieves:
- **mDice:** 94.7% on seen datasets.
- **mIoU:** 89.0% on Kvasir-SEG.
- **Boundary Precision:** 85.4% on challenging ETIS dataset.

### Qualitative Improvements
- Precisely segments intricate polyp boundaries, even in low-contrast regions.
- Strong generalization capability on unseen datasets.

---

## Getting Started
### Prerequisites
- **Python:** >= 3.8
- **PyTorch:** >= 2.0
- **CUDA:** Enabled GPU (e.g., NVIDIA A100)

### STEPS
1. Clone the repository:
   ```bash
   git clone https://github.com/username/SAM-MaGuP.git
   cd SAM-MaGuP
2. Install dependencies:
   ```bash
    pip install -r requirements.txt

4. Download the datasets: Kvasir-SEG, CVC-ClinicDB, ETIS, CVC-ColonDB, CVC-300. and organize the data structure as follows:
    ```bash
    data/
      ├── Kvasir-SEG/
      │   ├── train/
      │   │   ├── images/
      │   │   ├── masks/
      │   ├── test/
      │       ├── images/
      │       ├── masks/
      ├── CVC-ClinicDB/
      │   ...
5. Start training by running:
   ```bash
     python train.py --config configs/train_config.yaml
6. Run the inference script:
   ```bash
     python test.py --input data/test_images --output results/
###Citation
If you use this code or framework, please cite:
```bash
@inproceedings{SAM-MaGuP,
  title={Mamba Guided Boundary Prior Matters: A New Perspective for Generalized Polyp Segmentation},
  author={Dutta, Tapas K. and Majhi, Snehashis and Nayak, Deepak Ranjan and Jha, Debesh},
  booktitle={MICCAI 2025},
  year={2025}
}

