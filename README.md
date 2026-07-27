# Deep Learning Based Classification of Breast Ultrasound Images

## Project Overview

Breast cancer remains one of the most prevalent cancers affecting women worldwide. **Early detection is critical for improving patient survival rates and treatment outcomes.** This project develops an advanced deep learning-based image classification system specifically designed to analyze breast ultrasound images using the BUSI (Breast Ultrasound Images) dataset.

The system classifies ultrasound images into three distinct categories:
- **Normal**: Healthy breast tissue with no abnormalities
- **Benign**: Non-cancerous tumors or lesions
- **Malignant**: Cancerous tumors requiring immediate medical attention

## Problem Statement

Radiologists must manually analyze thousands of breast ultrasound images to identify potential cancer cases. This manual process is:
- Time-consuming and labor-intensive
- Prone to human error and fatigue
- Subject to inter-observer variability
- A bottleneck in clinical workflows

This project addresses these challenges by developing an automated, reliable, and scalable deep learning solution to assist radiologists in their diagnostic work.

## Dataset

**BUSI (Breast Ultrasound Images) Dataset**
- Contains annotated breast ultrasound images categorized as Normal, Benign, and Malignant
- Represents real-world clinical imaging data
- Exhibits class imbalance, a common challenge in medical imaging tasks

## Methodology

### Model Architecture
- **Base Model**: ResNet18 (Residual Network with 18 layers)
- **Framework**: PyTorch
- **Approach**: Transfer learning with fine-tuning on the ultrasound dataset

### Addressing Class Imbalance

Since medical datasets often have unequal class distributions, this project explores multiple techniques to improve model performance:

#### 1. **Baseline Model**
- Standard ResNet18 trained without addressing class imbalance
- Serves as a performance benchmark

#### 2. **Weighted Sampler**
- Assigns higher sampling probability to underrepresented classes
- Ensures the model sees balanced batches during training
- Helps prevent bias toward majority classes

#### 3. **Data Augmentation**
- Random rotations, flips, and scaling of images
- Increases dataset diversity and model robustness
- Reduces overfitting on limited medical data

#### 4. **Focal Loss**
- Specialized loss function designed for imbalanced datasets
- Down-weights easy examples and focuses on hard negatives
- Particularly effective for medical image classification

## Performance Metrics

The project evaluates all models using standard classification metrics:

| Metric | Description |
|--------|-------------|
| **Accuracy** | Overall correctness of predictions |
| **Precision** | True positives among all positive predictions (minimizes false alarms) |
| **Recall** | True positives among all actual positive cases (minimizes missed diagnoses) |
| **F1-Score** | Harmonic mean of precision and recall (balanced metric) |
| **Confusion Matrix** | Detailed breakdown of correct and incorrect predictions per class |

## Key Features

✅ **Comprehensive Comparison**: Evaluates multiple strategies for handling class imbalance
✅ **Medical Imaging Focus**: Uses real breast ultrasound images from BUSI dataset
✅ **Reproducible Research**: Clear methodology and documented code
✅ **Production-Ready Evaluation**: Uses clinically relevant metrics (precision, recall, F1)
✅ **Detailed Analysis**: Includes confusion matrices and class-wise performance metrics

## Project Structure

```
Breast_Ultrasound-image-classification/
├── README.md                          # This file
├── notebooks/                         # Jupyter notebooks with complete analysis
│   ├── data_exploration.ipynb         # Dataset exploration and visualization
│   ├── baseline_model.ipynb           # ResNet18 baseline without imbalance handling
│   ├── weighted_sampler.ipynb         # Training with weighted sampling
│   ├── data_augmentation.ipynb        # Data augmentation techniques
│   └── focal_loss.ipynb               # Focal loss implementation
└── results/                           # Model outputs and performance metrics
    ├── confusion_matrices/
    ├── training_curves/
    └── classification_reports/
```

## Installation & Requirements

### Dependencies
- Python 3.8+
- PyTorch 1.9+
- torchvision
- scikit-learn
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook

### Setup Instructions

```bash
# Clone the repository
git clone https://github.com/anjalirj27/Breast_Ultrasound-image-classification.git
cd Breast_Ultrasound-image-classification

# Install required packages
pip install -r requirements.txt

# Launch Jupyter notebooks
jupyter notebook
```

## Usage

1. **Download the BUSI Dataset**: Obtain the dataset from the official source
2. **Prepare Data**: Place images in the appropriate directory structure
3. **Run Notebooks**: Execute notebooks in order:
   - Start with data exploration
   - Run baseline model
   - Execute imbalance handling techniques
4. **Compare Results**: Review performance metrics and confusion matrices
5. **Visualize**: Generate plots for presentation and analysis

## Results Summary

This project demonstrates:
- How class imbalance affects medical image classification
- Effectiveness of various imbalance-handling strategies
- Performance trade-offs between different approaches
- Best practices for medical imaging applications

## Key Findings

- **Focal Loss** shows superior performance on minority classes (Malignant tumors)
- **Data Augmentation** improves generalization without additional labeled data
- **Weighted Sampling** provides a balance between computational efficiency and accuracy
- **Combined Approaches** often outperform individual techniques

## Clinical Significance

This work contributes to:
- **Decision Support Systems**: Helps radiologists make faster, more confident diagnoses
- **Accessibility**: Extends expert-level diagnostic capabilities to under-resourced regions
- **Research**: Provides benchmarks for medical imaging AI
- **Patient Care**: Enables earlier cancer detection and better treatment outcomes

## Limitations & Future Work

### Current Limitations
- Model performance depends heavily on dataset quality and diversity
- Ultrasound image quality varies by equipment and technician
- Results may not generalize to different ultrasound machines

### Future Enhancements
- [ ] Implement ensemble methods combining multiple models
- [ ] Test with 3D ultrasound volumes
- [ ] Develop explainability features (Grad-CAM visualization)
- [ ] Deploy as web application for clinical use
- [ ] Conduct multi-center validation studies
- [ ] Incorporate patient metadata for improved predictions

## License

This project is open-source and available for educational and research purposes.

## Acknowledgments

- BUSI Dataset creators and maintainers
- ResNet18 architecture (He et al., 2015)
- PyTorch and scientific Python communities
- Medical imaging research community

**Note**: This is an educational and research project. Any clinical application should be validated with medical professionals and comply with healthcare regulations (HIPAA, FDA, etc.).
