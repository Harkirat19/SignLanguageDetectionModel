# 🖐️ Sign Language Detection Model (Real-Time)

A real-time sign language recognition system that detects and translates specific hand gestures into readable text using computer vision and deep learning.

Developed by:  
👤 Harkirat Singh  
👤 Pranjal Parmar

---

## 📌 Project Overview

This project leverages **MediaPipe**, **OpenCV**, and an **LSTM-based neural network** to recognize three American Sign Language (ASL) gestures:

- ✋ "hello"
- 🙏 "thanks"
- ❤️ "I love you"

Users perform gestures live via webcam, and the system predicts the gesture in real time and constructs sentences on the screen. The system is trained entirely on custom-collected gesture data captured by the developers.

---

## ⚙️ Technologies Used

- **Python 3.9+**
- [OpenCV](https://opencv.org/)
- [MediaPipe](https://mediapipe.dev/)
- [TensorFlow / Keras](https://keras.io/)
- [NumPy](https://numpy.org/)
- [Scikit-learn](https://scikit-learn.org/)

---

## 🚀 How to Run

1. **Clone this repository**

   ```bash
   git clone https://github.com/Harkirat19/SignLanguageDetectionModel.git
   ```

2. **Install dependencies**

   ```bash
   pip install opencv-python mediapipe keras
   ```

3. **Set up the folder structure for gesture data**

   ```bash
   python folder_setup.py
   ```

   This will create the necessary folders under `MP_Data/` for each gesture (`hello`, `thanks`, `iloveyou`), including subfolders for each sequence.

4. **Collect training data using your webcam**

   ```bash
   python setup_training_testing_keypoints.py
   ```

   > 🎥 Follow the on-screen prompts to perform each gesture. The script will collect 30 sequences (videos) of 30 frames per gesture.

5. **Train the LSTM model**

   ```bash
   python training_testing.py
   ```

   This script loads the `.npy` keypoint data, trains the LSTM model, and saves the trained weights to `action.h5`.

6. **Run real-time gesture prediction**
   ```bash
   python make_predictions.py
   ```
   > 🖥️ A webcam window will open. The system will detect and predict your gestures live, displaying the recognized words and probability bars.

---

## 📚 References

1. **Guerin, G.** (2021). _Sign Language Recognition using MediaPipe_. Theodo Data & AI.  
   Retrieved from [https://data-ai.theodo.com/en/technical-blog/sign-language-recognition-using-mediapipe](https://data-ai.theodo.com/en/technical-blog/sign-language-recognition-using-mediapipe)

2. **Cabrera, E.** (2021). _Real-Time Sign-Language Detection System_. Medium.  
   Retrieved from [https://medium.com/@eacabrera3/real-time-sign-language-detection-system-e3d6cf49121a](https://medium.com/@eacabrera3/real-time-sign-language-detection-system-e3d6cf49121a)
