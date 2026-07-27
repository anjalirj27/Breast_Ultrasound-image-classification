For the full methodology, model comparisons, and results, see **[Deep Learning Based Classification of Breast Ultrasound Images.pdf](https://github.com/<your-username>/Breast-UltraSound-Image-Classificatoin/blob/main/_CS23B1068__Breast_UltraSound_Image_Classification.pdf)**.

# Deep Learning Based Classification of Breast Ultrasound Images

Breast cancer is one of the most prevalent cancers affecting women worldwide. Early de-
tection plays a critical role in improving patient survival rates. In this project, we develop a
deep learning based image classification system for breast ultrasound images using the BUSI
dataset. The objective is to classify ultrasound images into three categories: Normal, Benign,
and Malignant.
A baseline convolutional neural network model based on ResNet18 is first trained without
addressing dataset imbalance. Subsequently, different techniques for handling class imbalance
are explored, including oversampling using a weighted sampler, data augmentation, and focal
loss. The performance of these approaches is evaluated using standard classification metrics such
as accuracy, precision, recall, F1-score, and confusion matrices. The results allow comparison
of different strategies for improving classification performance on imbalanced medical imaging
datasets.
