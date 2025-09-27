# RMT-Regularization-Benchmark-on-CIFAR10
# Robust-RMT-CIFAR10

This repository benchmarks **Retentive Networks Meet Vision Transformers (RMT)** on **CIFAR-10**, exploring how various regularization methods improve generalization and robustness.

We experiment with:
Sharpness-Aware Minimization (SAM)
Sharpness-Aware Distilled Teachers (SADT)
CutMix Data Augmentation
Combined CutMix + SAM


## Project Structure
.
# RMT architecture and modules
├── cifarSAM.py                       # Training RMT with SAM
├── cifarcutmix.py                    # Training RMT with CutMix
├── cutmix_SAM.py                     # Training RMT with CutMix + SAM
├── sadtcifar.py                      # Training RMT with SADT
├── testcifar.py                      # Model evaluation
├── *.txt                             # Training logs (accuracy, loss)
├── checkpoint.pth                    # (optional) saved weights
├── README.md                         # This file
└── requirements.txt                  # Python dependencies


---

## Motivation

RMT (Retentive Networks Meet Vision Transformers) is a recent attention-free architecture that retains sequence information using gated recurrence and is competitive with transformers across vision and language tasks.

In this work, we evaluate how well RMT performs on CIFAR-10 under various regularization techniques:

- SAM improves generalization by finding flatter minima via sharpness-aware gradient updates.
- SADT (Sharpness-Aware Distilled Teachers) leverages teacher-student training to distill sharpness-aware knowledge for robust optimization.
- CutMix increases data diversity by mixing image regions and labels.
- Combined methods aim to further enhance robustness and generalization on small datasets.

---

##  Experiments

| Setup              | Description                        | Script             |
|--------------------|------------------------------------|--------------------|
| RMT + SAM          | Sharpness-Aware Minimization       | `cifarSAM.py`      |
| RMT + CutMix       | Mixed-region data augmentation     | `cifarcutmix.py`   |
| RMT + CutMix + SAM | Hybrid strategy                    | `cutmix_SAM.py`    |
| RMT + SADT         | Sharpness-Aware Distilled Teachers | `sadtcifar.py`     |



## ⚙️ Setup 

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Robust-RMT-CIFAR10.git
cd Robust-RMT-CIFAR10
