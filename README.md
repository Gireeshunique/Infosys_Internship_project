# 🎙️ Speech-to-Text + Diarization + Summarization Demo

This project is a **Streamlit-based web app** that performs:
1. **Speech-to-Text (ASR)** using OpenAI Whisper  
2. **Speaker Diarization** using Pyannote  
3. **Text Summarization** using a Hugging Face transformer model  

The app allows users to upload an audio file, process it, view the transcribed + diarized text, and download a generated summary.

---

## 🚀 Features

- 🎧 Upload audio in `.wav`, `.mp3`, `.m4a`, or `.flac`
- 🗣️ Speaker diarization (who spoke when)
- ✍️ Whisper-based transcription (ASR)
- 🧠 Summarization using `facebook/bart-large-cnn` or any Hugging Face model
- 💾 Download the summary as a text file
- ⚙️ Configurable model options via sidebar

---

## 🧩 Project Structure

.
├── app.py # Streamlit frontend + controller
├── pipeline.py # Core processing (ASR + diarization + summarization)
├── recordings/ # Folder for uploaded audio files (auto-created)
├── requirements.txt # All Python dependencies
└── README.md # Project documentation

## 📦 Installation Guide

### 1️⃣ Clone or Download This Repository
```bash
git clone https://github.com/your-username/speech-diarization-summary.git
cd speech-diarization-summary
2️⃣ Create a Virtual Environment
python -m venv venv


Activate it:

Windows:

venv\Scripts\activate


Mac/Linux:

source venv/bin/activate

3️⃣ Install Dependencies

Make sure pip is up-to-date, then install:

pip install -r requirements.txt


requirements.txt:

streamlit
openai-whisper
pyannote.audio
transformers
torch
torchaudio
librosa
soundfile

🔑 Hugging Face Token (Required for Diarization)

Visit https://huggingface.co/settings/tokens

Click New Token → Read access

Copy the token

Paste it into the Streamlit sidebar under “Hugging Face token (for pyannote)”

▶️ Run the Application
streamlit run app.py


Then open the link shown in your terminal (usually: http://localhost:8501)

🧠 How It Works

Upload Audio → The app saves and converts it to WAV if needed

Whisper Transcription → Converts speech to text

Pyannote Diarization → Detects and labels speakers

Summarizer → Generates a concise summary

Results Displayed → View transcript, speaker segments, and summary

💡 Example Output

Speaker Diarization Example

Speaker_1 [0.00 - 5.32]: Hello, everyone.
Speaker_2 [5.33 - 10.20]: Hi! Let's start the meeting.


Summary Example

The meeting began with introductions and discussion about project updates.

⚙️ Configuration Options

In the sidebar:

Select Whisper model: small, medium, large

Enter Hugging Face token (for diarization)

Change summarization model (e.g., facebook/bart-large-cnn, google/pegasus-xsum, etc.)

🧾 Notes

If diarization fails or token is missing, the app will still run transcription and summarization.

Use CPU by default (GPU will be used automatically if available).

All processed files are saved under recordings/.

🧑‍💻 Author

Developed by: Gireesh Boggala
Tech Stack: Streamlit · Whisper · Pyannote · Transformers · Torch
