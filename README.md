Overview
This project explores deep learning approaches to Speech Emotion Recognition (SER) using two architectures: CNN-GRU and CNN-LSTM with self-attention. The goal is to evaluate their effectiveness on noisy speech data, focusing on computational efficiency and classification accuracy.

Motivation
Emotion recognition enhances AI applications like virtual assistants, learning environments, and smart recommendations. While multimodal systems are more accurate, speech-only models are more practical and accessible in many real-world contexts (e.g., call centers), where visual or text data may not be available.

Challenges Addressed
Speaker variability: Emotion expression varies by age, gender, and culture.

Environmental noise: Real-world speech data is often distorted.

Data imbalance: Some emotions are underrepresented in datasets.

Solutions Used
Noise injection to simulate real-world environments.

Random oversampling to balance emotional class distribution.

Methodology
Dataset
CREMA-D: A labeled dataset of acted emotional speech with diverse speaker demographics.

Feature Extraction
Log-Mel Spectrograms: Represent speech with perceptually meaningful frequency scaling.

Delta and Delta-Delta Features: Capture dynamic temporal changes in speech.

Architectures
CNN-GRU

Convolutional layers extract spatial features from spectrograms.

GRU layers learn temporal dependencies.

CNN-LSTM with Self-Attention

Similar to CNN-GRU but includes LSTM layers and a self-attention mechanism to emphasize relevant time frames.

Results
CNN-GRU achieved a test accuracy of 55.88%.

CNN-LSTM + Attention scored 55.2%, but showed more signs of overfitting.

Emotions like anger, happiness, and neutral were recognized with higher accuracy.

Fear and disgust were harder to classify.
