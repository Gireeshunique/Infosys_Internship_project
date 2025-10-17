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

.
├── app.py

├── pipeline.py

├── requirements.txt

├── recordin
