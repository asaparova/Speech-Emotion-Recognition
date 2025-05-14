## Overview
This project investigates deep learning architectures for **Speech Emotion Recognition (SER)** using two models:
- **CNN-GRU**
- **CNN-LSTM with self-attention**

The models are evaluated under noisy and imbalanced conditions using the **CREMA-D** dataset.

---

## Motivation
Emotion recognition improves AI-human interaction in:
- Virtual assistants
- Learning environments
- Smart recommendation systems

While multimodal SER is more accurate, **speech-only models** are more practical for real-world scenarios where text and visual data are unavailable.

---

## Challenges in SER
- **Speaker variability** (age, gender, ethnicity)
- **Environmental noise**
- **Data imbalance** (some emotions underrepresented)

### Solutions
- **Noise injection** to simulate real conditions
- **Random oversampling** to balance emotional classes

---

## Dataset
- **CREMA-D**: 7442 audio files of emotional speech by actors.
- Speech is converted into **log-Mel spectrograms** with **delta** and **delta-delta** features.

---

## Model Architectures

### 1. CNN-GRU + Self-Attention
- Two 2D CNN layers for spatial features
- GRU layer for temporal modeling
- Multi-head self-attention for long-term dependency focus
- Final dense + softmax layers for classification

### 2. CNN-LSTM + Self-Attention
- Similar to CNN-GRU but uses LSTM instead of GRU
- More complex but potentially better memory of long-term patterns

---

## Methodology

### Preprocessing
- Normalize audio
- Standardize to 3 seconds
- Inject Gaussian noise
- Convert to log-Mel spectrograms with delta features
- Stack into 3D tensors: `(time × frequency × 3)`

### Data Handling
- Train/Validation/Test split: 80/10/10 or adjusted based on experiment
- Oversampling applied **after** splitting
- Fine-tuning with data augmentation (pitch shift, volume perturbation, SpecAugment)

---

## Results

| Model                     | Test Accuracy |
|--------------------------|---------------|
| CNN-GRU + Attention      | 55.88%        |
| CNN-LSTM + Attention     | 55.2%         |
| CNN-LSTM + Augmentation  | 50.14%        |

### Best Recognized Emotions:
- Anger
- Happiness
- Neutral

### Poorly Recognized Emotions:
- Fear
- Disgust

> Overfitting observed in all models. Proper preprocessing (splitting before oversampling) reduced inflated scores seen earlier.

---

## 🔗 Dataset Access
Download CREMA-D dataset:  
📁 [Google Drive Link](https://drive.google.com/drive/folders/1zqbsIxbpuTkNj7S2jjDld26DE9XeJyH3?usp=sharing)
