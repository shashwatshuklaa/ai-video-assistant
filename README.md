# 🎥 AI Video Assistant

An AI-powered video assistant that converts video/audio content into **transcripts, summaries, action items, key decisions, and interactive Q&A**.

The application uses **Whisper for transcription**, **LLMs for content analysis**, and **RAG (Retrieval-Augmented Generation)** to allow users to ask questions about the processed video.

## ✨ Features

* 🎬 **YouTube Video Processing** — Process videos directly from a YouTube URL.
* 📁 **Local File Processing** — Upload and analyze local audio/video files.
* 🎙️ **AI Transcription** — Convert speech into text using OpenAI Whisper.
* 🌐 **English & Hinglish Support** — Process content in English and Hinglish.
* 📝 **Automatic Summarization** — Generate concise summaries of video content.
* ✅ **Action Items** — Extract important tasks and follow-ups.
* 🎯 **Key Decisions** — Identify important decisions discussed in the video.
* ❓ **Open Questions** — Extract unresolved questions and topics.
* 💬 **AI Chat** — Ask questions about the video's content.
* 🔎 **RAG-based Retrieval** — Retrieve relevant sections of the transcript before generating answers.
* 🖥️ **Streamlit Interface** — Simple and interactive web interface.

## 🏗️ Project Architecture

The application follows a pipeline similar to:

```text
YouTube URL / Local Video
          │
          ▼
     Audio Extraction
          │
          ▼
       Whisper
     Transcription
          │
          ▼
   Language Processing
          │
          ▼
   ┌─────────────────┐
   │  AI Processing  │
   ├─────────────────┤
   │ • Summary       │
   │ • Action Items  │
   │ • Decisions     │
   │ • Questions     │
   └─────────────────┘
          │
          ▼
   Vector Database
          │
          ▼
     RAG Pipeline
          │
          ▼
       AI Chat
```

## 🛠️ Tech Stack

### Frontend

* **Streamlit**

### AI / Machine Learning

* **OpenAI Whisper** — Speech-to-text transcription
* **Mistral AI** — Large Language Model capabilities
* **Hugging Face** — Embeddings and NLP components

### RAG & Vector Database

* **LangChain**
* **ChromaDB**
* **Hugging Face Embeddings**

### Audio / Video Processing

* **yt-dlp** — YouTube video downloading
* **FFmpeg** — Audio/video processing
* **PyDub** — Audio manipulation

### Programming Language

* **Python 3.12**

## 📂 Project Structure

```text
AI-Video-Assistant-/
│
├── app.py
├── main.py
├── test.py
├── Requirements.txt
│
├── core/
│   ├── extractor.py
│   ├── rag_engine.py
│   ├── summarizer.py
│   ├── transcriber.py
│   └── vector_store.py
│
└── utils/
    └── audio_processor.py
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/shashwatshuklaa/ai-video-assistant.git
cd ai-video-assistant
```

### 2. Create a Conda environment

Python 3.12 is recommended.

```bash
conda create -n ai-video python=3.12
```

Activate the environment:

```bash
conda activate ai-video
```

### 3. Install FFmpeg

On Debian/Ubuntu:

```bash
sudo apt update
sudo apt install ffmpeg
```

Verify the installation:

```bash
ffmpeg -version
```

### 4. Install Python dependencies

```bash
pip install -r Requirements.txt
```

If required by your environment, install the additional packages used by the application:

```bash
pip install torchvision langchain-chroma
```

## 🔑 API Keys

The application requires API credentials for the AI services it uses.

Create a `.env` file in the project root:

```text
MISTRAL_API_KEY=your_mistral_api_key
SARVAM_API_KEY=your_sarvam_api_key
```

If your local configuration uses additional API keys, add them to `.env` as required.

### ⚠️ Security

**Never commit your `.env` file or API keys to GitHub.**

The repository includes `.env` in `.gitignore` to help prevent accidentally uploading secrets.

## 🚀 Running the Application

Activate the environment:

```bash
conda activate ai-video
```

Start Streamlit:

```bash
streamlit run app.py
```

Then open the local Streamlit URL shown in your terminal, typically:

```text
http://localhost:8501
```

## 💡 How It Works

1. Enter a **YouTube URL** or provide a local media file.
2. The application extracts/processes the audio.
3. Whisper converts the speech into a transcript.
4. The transcript is processed by the AI pipeline.
5. The application generates:

   * Summary
   * Action items
   * Key decisions
   * Open questions
6. Transcript content is stored in a vector database.
7. The RAG pipeline retrieves relevant information when you ask questions.
8. The AI generates answers based on the video's content.

## 📌 Example Use Cases

### 🎓 Learning

Summarize long educational lectures and ask questions about specific topics.

### 💼 Meetings

Extract action items, decisions, and unresolved questions from recorded meetings.

### 📺 YouTube Research

Quickly understand long-form YouTube videos without watching the entire video.

### 📚 Content Analysis

Turn video/audio content into searchable text and interact with it using AI.

## 🔮 Future Improvements

Possible improvements include:

* Support for additional languages
* Speaker identification
* Timestamp-based answers
* Improved transcript search
* Persistent vector database storage
* Video chapter generation
* Export summaries as PDF/Markdown
* Improved UI and user experience
* Support for additional LLM providers

## 👨‍💻 Author

**Shashwat Shukla**

GitHub:
https://github.com/shashwatshuklaa

---

⭐ If you find this project useful, consider giving the repository a star!
