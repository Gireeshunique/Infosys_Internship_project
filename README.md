# 🎙️ Speech-to-Text + Diarization + Summarization — Streamlit App

This project is a **Streamlit web app** that performs:
- **Speech-to-Text (ASR)** using OpenAI Whisper  
- **Speaker Diarization** using Pyannote  
- **Summarization** using a Hugging Face transformer model  

You can upload any audio file, the app will transcribe, detect who spoke when, summarize the conversation, and let you download the summary.

---

## 🚀 Features

✅ Upload `.wav`, `.mp3`, `.m4a`, `.flac` files  
✅ Whisper-based transcription  
✅ Pyannote speaker diarization  
✅ Text summarization (default: `facebook/bart-large-cnn`)  
✅ Summary download button  
✅ Configurable via Streamlit sidebar  

---

## 🧩 Project Structure

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
--> python -m venv venv

Activate it:

Windows:

venv\Scripts\activate

Mac/Linux:

source venv/bin/activate

3️⃣ Install Dependencies

requirements.txt:

streamlit
openai-whisper
pyannote.audio
transformers
torch
torchaudio
librosa
soundfile

Make sure pip is up-to-date, then install:

pip install -r requirements.txt

🔑 Hugging Face Token (Required for Diarization)

1.Visit https://huggingface.co/settings/tokens

2.Click New Token → Read access

3.Copy the token

4.Paste it into the Streamlit sidebar under “Hugging Face token (for pyannote)”

▶️ Run the Application

 --> streamlit run app.py

Then open the link shown in your terminal (usually: http://localhost:8501)

🧠 How It Works

Upload Audio → The app saves and converts it to WAV if needed

Whisper Transcription → Converts speech to text

Pyannote Diarization → Detects and labels speakers

Summarizer → Generates a concise summary

Results Displayed → View transcript, speaker segments, and summary

💡 Example Output :

Speaker Diarization Example

Speaker_1 [0.00 - 5.32]: Hello, everyone.
Speaker_2 [5.33 - 10.20]: Hi! Let's start the meeting.

Summary Example

The meeting began with introductions and discussion about project updates.

⚙️ Configuration Options :

1.Select Whisper model: small, medium, large

2.Enter Hugging Face token (for diarization)

3.Change summarization model (e.g., facebook/bart-large-cnn, google/pegasus-xsum, etc.)

🧾 Notes :

> If diarization fails or token is missing, the app will still run transcription and summarization.

> Use CPU by default (GPU will be used automatically if available).

> All processed files are saved under recordings/.

🧑‍💻 Author :

Developed by: Gireesh Boggala
Tech Stack: Streamlit · Whisper · Pyannote · Transformers · Torch
Tools : VS Studio Code , Google Colab , Streamlit
Laguages : Python 
