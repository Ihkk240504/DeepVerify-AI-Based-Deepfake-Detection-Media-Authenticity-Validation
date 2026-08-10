# DeepVerify: AI Framework for Deepfake Detection and Media Authenticity Validation

DeepVerify is a deep learning-based system that detects manipulated (deepfake) videos and classifies altered audio content, with results served through a simple Django web interface.

## Overview

The rise of deepfake technology has made it increasingly difficult to trust digital video and audio content. DeepVerify addresses this by combining computer vision and audio signal analysis to flag manipulated media:

- **Video analysis**: A Convolutional Neural Network (CNN) built with TensorFlow is trained on real and fake video datasets to learn facial features and detect signs of tampering.
- **Audio analysis**: Audio features are extracted using Librosa and passed through Recurrent Neural Networks (SimpleRNN and LSTM) to determine whether the audio is genuine or altered.
- **Web interface**: A Django application lets users upload a video or audio file and instantly view the authenticity result.

## Tech Stack

- **Language**: Python
- **Deep Learning**: TensorFlow, Keras
- **Audio Processing**: Librosa
- **Models**: CNN (video), SimpleRNN & LSTM (audio)
- **Web Framework**: Django
- **Frontend**: HTML, CSS

## Features

- Upload and analyze video files for facial manipulation
- Upload and analyze audio files for signs of tampering
- Real-time authenticity results through a web interface
- Modular design separating model training from the web application

## How It Works

1. Video/audio files are uploaded via the Django web interface.
2. The video is processed frame-by-frame and passed through the trained CNN model.
3. The audio is converted into features (e.g., MFCCs) using Librosa and passed through the RNN/LSTM model.
4. The system returns a classification: **Real** or **Fake/Manipulated**.

## Installation

```bash
git clone https://github.com/yourusername/deepverify.git
cd deepverify
pip install -r requirements.txt
python manage.py runserver
```

Then open `http://127.0.0.1:8000/` in your browser.

## Project Structure

```
deepverify/
├── models/           # Trained CNN and RNN/LSTM model files
├── app/              # Django app (views, templates, urls)
├── static/           # CSS/JS files
├── notebooks/        # Model training notebooks
├── requirements.txt
└── manage.py
```

## Future Work

- Improve detection accuracy on low-resolution or heavily compressed videos
- Add support for real-time webcam-based detection
- Expand audio classification to cover more manipulation techniques

## License

This project is for academic/educational purposes.
