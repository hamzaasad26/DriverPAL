# DriverPAL: AI-Powered Driver Monitoring System

**DriverPAL** is an AI-driven driver assistance application developed by students at the National University of Computer and Emerging Sciences, Islamabad Campus. It leverages computer vision and deep learning to monitor drivers in real-time, enhancing road safety and personalizing the in-vehicle experience.

---

## 🚗 Overview

DriverPAL utilizes webcam-based facial analysis to:

- Estimate **Age**
- Classify **Gender**
- Recognize **Emotions**

These insights enable intelligent UI adjustments and emotional support actions while driving.

---

## 🧠 Core Components

### 1. Age Estimation Model

- **Dataset**: MORPH-II  
- **Preprocessing**:
  - Face cropping using MTCNN or Haar Cascade
  - Resizing to 224×224 pixels
  - Normalization with ImageNet mean and standard deviation
  - Feature augmentation using CLAHE, LBP, and HOG
- **Model**: Modified ResNet-50 adapted for 6-channel input
- **Training**:
  - Loss Function: Smooth L1 (Huber Loss)
  - Optimizer: Adam
  - Learning Rate Scheduler: Cosine Annealing
  - Oversampling to address age imbalance
- **Performance**:
  - Mean Absolute Error (MAE): 2.36 years
  - Cumulative Score: 83% within ±5 years, 98% within ±10 years

### 2. Gender Classification Model

- **Dataset**: CelebA Gender Recognition Dataset  
- **Preprocessing**:
  - Image resizing to 100×100 pixels
  - Normalization to [0, 1] range
  - Data augmentation using Keras's ImageDataGenerator (rotation, shifts, flips, zoom, brightness adjustment)
- **Model**: Convolutional Neural Network (CNN) built with Keras Sequential API
- **Training**:
  - Loss Function: Binary Crossentropy
  - Optimizer: Adam
  - Epochs: 10
  - Batch Size: 32
- **Performance**:
  - Final Test Accuracy: 92.8%

### 3. Emotion Recognition Model

- **Dataset**: FER-2013  
- **Models Compared**:
  - **Base + CLAHE Model**:
    - Applied CLAHE preprocessing
    - Achieved ~54% validation accuracy
  - **Optimal Detector Model**:
    - Avoided additional preprocessing
    - Deeper CNN architecture with Batch Normalization and L₂ regularization
    - Achieved ~64% validation accuracy
- **Conclusion**: Avoiding over-processing and employing a robust architecture led to better performance.

---

## 🚀 Application Features

- **Real-Time Face Analysis**: Continuous detection and processing of facial cues using OpenCV.
- **Deep Learning Models**:
  - TensorFlow-based Gender and Emotion classifiers
  - PyTorch-based Age Group model
- **Emotion-Based Music Recommendations**: Spotify integration to boost mood during stress or sadness.
- **Dynamic UI Personalization**: Interface adapts based on detected age and gender.
- **Conversational Support**: Voice interaction is triggered during emotional distress (e.g., anger, sadness) for safety reassurance.

---

## 🎯 Purpose

To promote emotional well-being, driver focus, and personalized engagement using AI. The application proactively responds to negative emotional states and enhances comfort through customized interactions.

---

## 🔮 Future Enhancements

- Fatigue and drowsiness detection  
- Expanded speech-based interaction  
- Long-term emotional pattern tracking


---

> *DriverPAL showcases a powerful fusion of machine learning and user empathy, setting a foundation for emotionally aware automotive systems.*
