This project processes video files to automatically transcribe spoken content and detect the speaker’s emotional state. It leverages OpenAI’s Whisper model for speech recognition and traditional audio processing techniques (MFCCs & pitch) for emotion classification using a simple SVM model.

🧠 Core Technologies
Whisper – State-of-the-art speech recognition by OpenAI

Librosa – Audio analysis (MFCCs, pitch extraction)

MoviePy – Audio extraction from MP4 files

scikit-learn – Machine learning model for emotion classification

🔁 How It Works
Convert MP4 to WAV
The input video is converted to a WAV file using moviepy.

Transcribe Speech
Whisper model processes the audio and returns a transcription along with the detected language.

Extract Features for Emotion
Extracts MFCCs and pitch from the audio. These are statistical summaries (mean) used as emotion features.

Classify Emotion
An SVM classifier (trained on dummy data here) predicts the speaker’s emotional tone: happy, sad, angry, or neutral.

Display Output
Shows transcription, detected emotion, and language.

⚙️ Setup
Install dependencies:

bash
Copy
Edit
pip install openai-whisper librosa moviepy scikit-learn numpy
Also install FFmpeg (required by Whisper and MoviePy):

bash
Copy
Edit
# Debian/Ubuntu
sudo apt install ffmpeg

# macOS
brew install ffmpeg
▶️ Running the Code
Update the audio_path variable in the script to point to your MP4 video:

python
Copy
Edit
audio_path = "your_video_file.mp4"
emotion_aware_speech_recognition(audio_path)
Example output:

vbnet
Copy
Edit
Transcription: Let's get started with our project!
Detected Emotion: neutral
Language Detected: en
