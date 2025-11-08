# Deep Learning Project (DLP)

> **Course:** Deep Learning  
> **Authors:** i221178, i221237

---

## Overview

This repository contains two deep learning assignments covering **computer vision** and **natural language processing** tasks.

| Question | Topic | Models |
|----------|-------|--------|
| [Q1](Q1/) | Waste Object Detection & Segmentation | YOLOv8, U-Net |
| [Q2](Q2/) | Urdu Poetry Text Generation | RNN, LSTM, Transformer |

---

## Q1 — Waste Object Detection & Segmentation

Detects and segments waste items from real-world scenes using the [TACO dataset](https://www.kaggle.com/datasets/kneroma/tacotrashdataset).

- **Object Detection** with YOLOv8n (trained from scratch)
- **Semantic Segmentation** with a custom U-Net (encoder-decoder with skip connections)
- Includes EDA, data augmentation analysis, and comprehensive evaluation (mAP, IoU, Dice)

👉 See [Q1/README.md](Q1/README.md) for full details.

## Q2 — Urdu Poetry Text Generation

Comparative analysis of sequence models and optimizers for generating Urdu poetry.

- **3 Architectures**: RNN, LSTM, Transformer
- **3 Optimizers**: Adam, RMSprop, SGD
- **9 Combinations** evaluated on perplexity and qualitative scoring
- **Best Result**: Transformer + SGD — Qualitative Score: 3.66/5

👉 See [Q2/README.md](Q2/README.md) for full details.

---

## Tech Stack

- Python 3.8+
- PyTorch 2.0+
- Ultralytics (YOLOv8)
- OpenCV, Albumentations
- Matplotlib, NumPy, Pandas

## Repository Structure

```
.
├── Q1/
│   ├── checkpoints/          # Model weights (gitignored)
│   ├── notebooks/
│   │   ├── Q1_optimized.ipynb
│   │   └── Q1_unet_modifications.ipynb
│   └── README.md
├── Q2/
│   ├── notebooks/
│   │   └── q2.ipynb
│   ├── results/              # Training curves, CSVs, heatmaps
│   └── README.md
├── .gitignore
└── README.md
```

## Setup

```bash
pip install torch torchvision ultralytics opencv-python matplotlib numpy pandas pillow pycocotools albumentations tqdm tensorboard
```

## License

This project is for educational purposes as part of a Deep Learning course assignment.
