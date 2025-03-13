# 🎓 Vietnamese Sign Language Recognition System

<div align="center">

<p align="center">
  <img src="images/logo.png" alt="DaiNam University Logo" width="200"/>
  <img src="images/AIoTLab_logo.png" alt="AIoTLab Logo" width="170"/>
</p>

[https://github.com/drkhanusa/DNU_PlagiarismChecker/blob/main/docs/images/logo.png](https://github.com/drkhanusa/DNU_PlagiarismChecker/blob/main/docs/images/logo.png?raw=true)
https://github.com/drkhanusa/DNU_PlagiarismChecker/raw/main/docs/images/AIoTLab_logo.png
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-red?style=for-the-badge)](https://dainam.edu.vn)

</div>

<h3 align="center">🔬 Empowering Communication Through AI-Driven Sign Language Recognition</h3>

<p align="center">
  <strong>A Real-Time Vietnamese Sign Language Recognition System Powered by Mediapipe and SignLSTM</strong>
</p>

<p align="center">
  <a href="#-architecture">Architecture</a> •
  <a href="#-key-features">Features</a> •
  <a href="#-tech-stack">Tech Stack</a> •
  <a href="#-installation">Installation</a> •
  <a href="#-getting-started">Getting Started</a> •
  <a href="#-documentation">Docs</a>
</p>

## 🏗️ Architecture

<p align="center">
  <img src="docs/images/architecture_signlstm.png" alt="System Architecture" width="800"/>
</p>

The system employs a multi-stage architecture:

1. **📹 Input Processing Layer**: Captures webcam video at 1280x720 resolution and extracts 1662 keypoints (33 pose, 468 face, 21 left hand, 21 right hand) using Mediapipe Holistic.
2. **🧠 Model Layer**: Processes sequences of 30 frames with a two-layer SignLSTM model (64 units, dropout 0.2) for action recognition.
3. **🔊 Output Layer**: Displays predicted actions on-screen with styled landmarks and plays corresponding audio if confidence exceeds 0.8 for at least 1 second.

## ✨ Key Features

### 🧠 Advanced AI Technology
- **SignLSTM Model**: Two-layer LSTM (64 units each, dropout 0.2) with Dense layers (32 units ReLU, 10 units Softmax) for accurate action classification, achieving 90% test accuracy.
- **Mediapipe Holistic**: Extracts 1662 keypoints (pose, face, hands) with min detection/tracking confidence of 0.5 for robust gesture detection.
- **Real-time Recognition**: Processes 30-frame sequences with an inference time of ~30ms, supporting 10 Vietnamese sign language actions.

### ⚡ High-Performance Architecture
- **Efficient Training**: Uses Adam optimizer (learning rate 0.0001), categorical crossentropy loss, and early stopping (patience 20) to prevent overfitting.
- **Action Stability Detection**: Ensures actions are stable (≥ 1 second) before triggering audio playback, with a 2-second cooldown to prevent overlap.
- **Scalable Design**: Supports 10 actions with 100 sequences per action (30 frames each), expandable with additional data.

### 📊 Comprehensive Analysis
- **Styled Visualizations**: Displays keypoints with custom colors (e.g., orange for pose, blue for hands) and on-screen action labels in Vietnamese using Arial font.
- **Audio Feedback**: Plays pre-recorded `.mp3` files (e.g., `xin_chao.mp3`) for recognized actions, enhancing communication.
- **Action Recognition**: Recognizes 10 actions: "null", "xin chao", "cam on", "xin loi", "hanh phuc", "tuyet voi", "yeu thuong", "ghet", "biet on", "tam biet".

## 🔧 Tech Stack

<div align="center">

### Core Technologies
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=yellow)](https://www.python.org/)
[![Mediapipe](https://img.shields.io/badge/Mediapipe-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://mediapipe.dev/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)
### Supporting Libraries
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pygame](https://img.shields.io/badge/Pygame-000000?style=for-the-badge&logo=pygame&logoColor=yellow)](https://www.pygame.org/)
[![Pillow](https://img.shields.io/badge/Pillow-000000?style=for-the-badge&logo=python&logoColor=white)](https://python-pillow.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

</div>

## 📥 Installation

### 🛠️ Prerequisites

- 🐍 **Python** `3.8+` - Core programming language.
- 📹 **Webcam** - For real-time gesture capture (recommended resolution: 1280x720).
- 💾 **RAM** `4GB+` - Recommended for smooth performance.
- 💻 **CPU** `2+ cores` - For video processing and inference.
- 🖴 **Storage** `2GB+` - For data, models, and audio files.

### ⚙️ Project Setup

1. 📦 **Clone Repository**
   ```bash
   git clone https://github.com/DangTruongDuong/sign-language-detection-using-lstm
   cd sign-language-detection-using-lstm
