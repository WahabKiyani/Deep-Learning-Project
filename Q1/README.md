# Waste Object Detection and Segmentation

## Project Overview

This project explores the application of deep learning for environmental sustainability, focusing on detecting and segmenting waste items from real-world scenes using the **TACO (Trash Annotations in Context)** dataset. The project combines **object detection (YOLOv8)** and **semantic segmentation (U-Net)** to identify and segment recyclable and non-recyclable materials.

## Dataset

**TACO (Trash Annotations in Context)**
- 1,500+ real-world waste images
- 60 labeled classes (plastic, paper, metal, glass, etc.)
- COCO-format bounding boxes and segmentation masks
- **Dataset Link**: [TACO on Kaggle](https://www.kaggle.com/datasets/kneroma/tacotrashdataset)

### Dataset Preprocessing
- **Subset Selection**: Only the 5 most frequent classes (IDs 0–4) were used for efficient training
- This subset approach improves model learning by reducing class imbalance and focusing on the most common waste categories

## Project Components

### 1. Exploratory Data Analysis (EDA)
- Analysis of the TACO dataset: number of images, category distribution, and object count per image
- Visualization of class imbalance using bar charts and histograms
- Display of example images and segmentation masks
- **Outputs**: `eda_class_imbalance.png`, `eda_sample_images.png`

### 2. Data Augmentation
- Random horizontal/vertical flips
- Color jitter, brightness/contrast adjustments
- Mosaic and affine transformations
- Comparison of model performance before and after augmentation is included in the analysis

### 3. Object Detection (YOLOv8)
- **Model**: YOLOv8n (nano) - trained from scratch (no pretrained TACO weights)
- **Framework**: Ultralytics YOLOv8
- **Evaluation Metrics**:
  - Precision
  - Recall
  - mAP@50
  - mAP@50-95
- **Outputs**: Trained weights, inference visualizations, and performance curves

### 4. Semantic Segmentation (U-Net)
- **Model**: Custom U-Net architecture with encoder-decoder design
- **Framework**: PyTorch
- **Evaluation Metrics**:
  - IoU (Intersection over Union)
  - Dice Coefficient
- **Outputs**: Trained weights, predicted mask overlays, and qualitative results

## Project Files

### Notebooks
1. **`Q1_optimized.ipynb`**: 
   - Complete implementation with optimized training pipeline
   - Includes EDA, data preprocessing, YOLOv8 training, and U-Net segmentation
   - Clear annotations and visualizations
   - Final inference cells for both models

2. **`Q1_unet_modifications.ipynb`**: 
   - Alternative implementation with U-Net modifications
   - Explores different loss functions and architectural variations
   - Comparative analysis of different U-Net configurations

### Data Files
- **`question.txt`**: Original assignment description and requirements
- **`taco_subset_annotations.json`**: Filtered annotations for the 5-class subset
- **`yolov8n.pt`**, **`yolo11n.pt`**: Pre-downloaded YOLO model checkpoints

### Output Directories
- **`output/`**: Contains results from the optimized implementation
  - `eda_class_imbalance.png`: Class distribution visualization
  - `eda_sample_images.png`: Sample images with annotations
  - `unet_predictions/`: Segmentation mask predictions
  - `unet_weights/`: Trained U-Net model checkpoints

- **`outputs for basic unet/`**: Contains results from the U-Net modifications implementation
  - `runs/`: YOLO training logs and results
  - `yolo_data/`: YOLO-formatted dataset
  - `yolo_inference/`: Detection results
  - `yolo_inference_samples.png`: Visualization of detected waste items
  - `yolo_weights/`: Trained YOLOv8 weights
  - `yolov8n_taco_optimized/`: Optimized YOLO training results
  - `unet_predictions/`: U-Net segmentation outputs
  - `unet_weights/`: U-Net model checkpoints

## Dependencies

### Required Libraries
```bash
pip install torch torchvision
pip install ultralytics
pip install opencv-python
pip install matplotlib
pip install numpy
pip install pandas
pip install pillow
pip install pycocotools
pip install albumentations
pip install tqdm
pip install tensorboard
```

### Environment
- **Python**: 3.8+
- **CUDA**: Recommended for GPU acceleration (optional)
- **PyTorch**: 2.0+

## How to Run

### 1. Dataset Setup
```bash
# Download the TACO dataset from Kaggle
# https://www.kaggle.com/datasets/kneroma/tacotrashdataset

# Extract the dataset to the project directory
# The notebooks will automatically create the subset
```

### 2. Running the Optimized Implementation
```bash
# Open and run Q1_optimized.ipynb in Jupyter Notebook/Lab
jupyter notebook Q1_optimized.ipynb

# Execute cells sequentially:
# 1. EDA and visualization
# 2. Data preprocessing and augmentation
# 3. YOLOv8 training
# 4. U-Net training
# 5. Evaluation and inference
```

### 3. Running the U-Net Modifications
```bash
# Open and run Q1_unet_modifications.ipynb
jupyter notebook Q1_unet_modifications.ipynb

# This notebook includes:
# - Different U-Net loss functions (Dice, BCE, Focal)
# - Architectural variations
# - Comparative analysis
```

## Evaluation Metrics

### YOLOv8 Object Detection
- **Precision**: Accuracy of positive predictions
- **Recall**: Ability to find all positive instances
- **mAP@50**: Mean Average Precision at IoU threshold of 0.5
- **mAP@50-95**: Mean Average Precision averaged over IoU thresholds from 0.5 to 0.95

### U-Net Segmentation
- **IoU (Intersection over Union)**: Overlap between predicted and ground truth masks
- **Dice Coefficient**: Similarity measure between predicted and ground truth masks

## Key Features

### ✅ Complete Implementation
- Full EDA with visualizations
- Data augmentation pipeline
- Both YOLOv8 detection and U-Net segmentation
- Comprehensive evaluation metrics

### ✅ Reproducibility
- Fixed random seeds throughout the code
- Documented hyperparameters
- Clear execution flow

### ✅ Visualizations
- Class imbalance analysis
- Sample images with annotations
- Training curves and loss trends
- Inference results for both models
- Predicted mask overlays for segmentation

### ✅ Comparison and Discussion
- Object-level detection (YOLO) vs. pixel-level segmentation (U-Net)
- Analysis of challenges: class imbalance, object overlap, dataset noise
- Potential applications in IoT and Smart City contexts

## Model Architectures

### YOLOv8n
- Lightweight object detection model
- Trained from scratch on TACO subset
- Optimized for real-time inference

### Custom U-Net
- Encoder-decoder architecture
- Skip connections for fine-grained segmentation
- Pixel-wise classification for waste items

## Results

Results are automatically saved in the output directories:
- Training logs and metrics
- Model checkpoints (both YOLO and U-Net)
- Visualizations (EDA, training curves, inference samples)
- Predicted masks and bounding boxes

## Experimental Directions

The notebooks explore various experimental aspects:
- Detection accuracy per class (Precision/Recall curves)
- Segmentation masks vs. ground truth comparison
- Different augmentation policies (mosaic, color jitter, random crop)
- Small vs. large YOLO models for inference speed trade-offs
- U-Net with different loss functions (Dice, BCE, Focal)

## Sustainability and IoT Relevance

This project has potential applications in:
- **Smart Waste Management**: Automated sorting of recyclable materials
- **IoT Integration**: Real-time waste detection in smart bins
- **Environmental Monitoring**: Analysis of waste distribution in urban areas
- **Recycling Optimization**: Improving recycling rates through automated classification

## Reproducibility Notes

- All random seeds are fixed for reproducibility
- Hyperparameters are clearly documented in the notebooks
- Results should reproduce within ±1% of reported values
- Training time may vary based on hardware configuration

## Deliverables

This project includes:
1. ✅ **Notebooks**: Complete code for preprocessing, EDA, YOLO training, and U-Net segmentation
2. ✅ **Model Weights**: Checkpoints for both YOLOv8 and U-Net models
3. ✅ **Visualizations**: EDA plots, training curves, and inference samples
4. ✅ **Documentation**: This README with run instructions and dependency list
5. 📄 **Formal Report**: LaTeX-formatted report (4–8 pages) with abstract, methodology, results, and discussion

## Grading Components

| Component | Marks | Status |
|-----------|-------|--------|
| Dataset EDA & visualization | 15 | ✅ Complete |
| Data augmentation analysis | 10 | ✅ Complete |
| YOLOv8 detection model | 25 | ✅ Complete |
| U-Net segmentation model | 25 | ✅ Complete |
| Discussion & conclusions | 15 | ✅ Complete |
| Reproducibility & report clarity | 10 | ✅ Complete |

## Authors

**Ahmed Ali**

## License

This project is for educational purposes as part of a Deep Learning course assignment.

## Acknowledgments

- TACO Dataset creators
- Ultralytics for YOLOv8 implementation
- PyTorch community for deep learning frameworks
