# Nvidiafinalproject

The goal of the project is to classify audios like "pen", "give me the pen" and some random noices. There is in total 42 samples of voices of 5 seconds each, the code uses a model called DecisionTreeClassifier from scikit-learn that extracts the audio from the folder "Random noices" and "Audios" to know wich one to follow and wich one to ignore

## The Algorithm

The project uses Decision Tree classifier, an algorithm that interprests effectively small classification tasks. A decision Tree splits data into brancjes based on the event. At each node it chooses the best feature e and threshold that separates the data to minimize classification error. Each internal node represents a decision based on an audio fearue and each leaf node represents a clase label: "pen"or "random".

## Running this project
Clone repository
git clone https://github.com/yourusername/audio-pen-classifier.git
cd audio-pen-classifier

Install
Python 3.8+
pip install -r requirements.txt
scikit-learn
numpy
pandas
librosa
matplotlib

Add audio samples

Extract audio features
Extract MFCCs using a script (e.g., extract_features.py):
python src/extract_features.py

Train model
python src/train_model.py
This script:
Loads extracted features
Trains a DecisionTreeClassifier
Prints training and cross-validation metrics
Example output:
Training Accuracy: 100%
Cross-Validation Scores: [0.6 1.0 1.0 1.0 0.75]
Mean Accuracy: 0.87

Predict on new audio
To classify a new clip:
python src/predict.py --file new_clip.wav
Output:
Predicted label: pen

Some improvements that could be done to the model is to add more random noices data in to avoid overliftting. Attach microphone to a computer such as a Jetson Nano to detect the users real time noice.

