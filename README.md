# Drowsiness Detection System using CNN and OpenCV

This project is a Drowsiness Detection System that uses a Convolutional Neural Network (CNN) and OpenCV to monitor a user's eyes through a webcam and detect signs of drowsiness in real-time.

## 📁 Project Structure

* `cnn.ipynb` – CNN model training for eye state classification
* `image.ipynb` – Image capture and preprocessing utilities
* `Run_App.ipynb` – Main application integrating webcam and detection
* `requirements.txt` – Python dependencies

## 🔍 Project Description

The system works by:

* Capturing video frames using a webcam via OpenCV
* Detecting the eyes using Haar cascades
* Classifying whether eyes are open or closed using a trained CNN model
* Raising an alert (e.g., sound) if drowsiness is detected over consecutive frames

## 🧠 CNN Model

The Convolutional Neural Network (implemented in `cnn.ipynb`) is trained to classify eye states:

* **Open**
* **Closed**

It includes:

* Convolutional and MaxPooling layers
* Dropout for regularization
* Dense output layer for binary classification

## 📸 Image Capture & Processing

The `image.ipynb` notebook:

* Loads and preprocesses eye images (grayscale, resize to 28x28)
* Optionally performs data augmentation
* Prepares training/validation datasets

## 🚨 Drowsiness Detection Logic

Implemented in `Run_App.ipynb`:

* Streams webcam frames via OpenCV
* Detects eye regions using Haar cascade classifier
* Passes preprocessed eyes into the CNN model
* Counts closed-eye frames, and if they cross a threshold, plays a warning sound

## ✅ Requirements

Install all dependencies using pip:

```bash
pip install -r requirements.txt
```

Key packages:

* `opencv-python`
* `tensorflow`
* `keras`
* `matplotlib`, `numpy`, `pandas`
* `pygame`, `playsound`

## 🚀 How to Run

1. **Install Python 3.8+** and dependencies:

```bash
pip install -r requirements.txt
```

2. **Train the CNN model**:

Open and run:

```bash
cnn.ipynb
```

> Saves the trained model as `.h5`

3. **Optional: Preprocess or inspect dataset**:

Run:

```bash
image.ipynb
```

4. **Start the Drowsiness Detection App**:

Run:

```bash
Run_App.ipynb
```

> This starts the webcam and begins monitoring eye activity.

## 🔊 Alert System

If the eyes are classified as closed for too many consecutive frames, an alarm will sound via `playsound`.

## 📄 License

This project is intended for research, learning, and demonstration purposes only.

---

Made with ❤️ using OpenCV, TensorFlow, and Keras
