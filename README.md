# Voice Assistant with OpenAI GPT-3 & IBM Watson

## Conversational AI web app: Speak, listen, and chat with GPT-3, powered by IBM Watson Speech Services

[Features](#-features) • [Tech Stack](#-tech-stack) • [How It Works](#-how-it-works) • [Screenshots](#-screenshots) • [Prerequisites](#-prerequisites) • [Getting Started](#-getting-started) • [Learning Objectives](#-learning-objectives) • [Acknowledgements](#-acknowledgements)

---

## ✨ Features

- 🎤 **Voice Interaction:** Speak to the assistant and hear its responses.
- 🧠 **Intelligent Responses:** Powered by OpenAI's `gpt-3.5-turbo` model for natural and coherent conversations.
- 🗣️ **High-Quality Speech Services:** Utilizes IBM Watson for fast and accurate Speech-to-Text and Text-to-Speech conversion.
- 🌐 **Responsive Web Interface:** Clean, modern UI with HTML, CSS, and JavaScript.
- 🎨 **Light & Dark Modes:** User-friendly theme switching for comfort.
- 📦 **Containerized:** Includes a `Dockerfile` for easy setup and deployment.
- 🐍 **Python Backend:** Built on the lightweight Flask web framework.

---

## 🛠️ Tech Stack

- **Backend:** Python, Flask
- **Frontend:** HTML, CSS, JavaScript, JQuery, Bootstrap, Font Awesome
- **AI Services:**
  - OpenAI API (`gpt-3.5-turbo`)
  - IBM Watson Speech to Text
  - IBM Watson Text to Speech
- **Containerization:** Docker

---

## 🧩 How It Works

1. **Frontend (JavaScript):** Captures microphone audio when the user clicks the record button.
2. **Speech-to-Text:** Audio is sent to Flask backend's `/speech-to-text` endpoint, which uses IBM Watson Speech-to-Text API.
3. **User Prompt:** Transcribed text is returned and displayed as the user's message.
4. **Process Prompt:** Frontend sends the text to backend's `/process-message` endpoint.
5. **OpenAI GPT-3:** Backend sends the prompt to OpenAI API for a response.
6. **Text-to-Speech:** OpenAI's response is sent to IBM Watson Text-to-Speech API for audio synthesis.
7. **Final Response:** Backend returns the text and audio (base64) to the frontend.
8. **Playback:** Frontend displays the assistant's response and plays the audio.

---

## 🚀 Prerequisites

- **Docker:** Ensure Docker is installed.
- **Git:** To clone the repository.
- **API Keys:**
  - **OpenAI:** Create an account and get an API key.
  - **IBM Cloud:** Provision Speech to Text and Text to Speech services, get their URLs and API keys.

> **Note for CognitiveClass.ai users:**
> This project was originally a guided project for the [CognitiveClass.ai](https://cognitiveclass.ai/) platform, which provides pre-configured IBM Watson services. If running outside that environment, follow the steps above to obtain your own API keys and service URLs.

---

## 🏁 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ibm-developer-skills-network/bkrva-chatapp-with-voice-and-openai-outline.git
mv bkrva-chatapp-with-voice-and-openai-outline chatapp-with-voice-and-openai-outline
cd chatapp-with-voice-and-openai-outline
```

### 2. Configure the Services

Edit `worker.py` to add your API keys and service URLs:

- **IBM Watson Speech-to-Text:** In `speech_to_text`, update `base_url` with your service URL.
- **IBM Watson Text-to-Speech:** In `text_to_speech`, update `base_url` with your service URL.
- **OpenAI:** Ensure your API key is set (typically via environment variable).

Example:

```python
# worker.py

def speech_to_text(audio_binary):
    base_url = 'https://YOUR-WATSON-STT-URL'  # <-- REPLACE WITH YOUR URL
    api_url = base_url + '/speech-to-text/api/v1/recognize'
    # ...

def text_to_speech(text, voice=""):
    base_url = 'https://YOUR-WATSON-TTS-URL'  # <-- REPLACE WITH YOUR URL
    api_url = base_url + '/text-to-speech/api/v1/synthesize?output=output_text.wav'
    # ...
```

### 3. Build and Run with Docker

```bash
# Build the Docker image
docker build . -t voice-chatapp-powered-by-openai

# Run the container, mapping port 8000
docker run -p 8000:8000 voice-chatapp-powered-by-openai
```

> **Tip:** If you make code changes, stop the container (Ctrl+C), rebuild, and rerun.

### 4. Test Your Assistant

Open your browser and go to [http://localhost:8000](http://localhost:8000) to interact with your voice assistant!

---

## 🎯 Learning Objectives

- Integrate OpenAI GPT-3 with a web application
- Use IBM Watson APIs for speech recognition and synthesis
- Build a full-stack app with Flask and modern frontend tools
- Containerize and deploy with Docker

---

## 🙏 Acknowledgements

- [OpenAI](https://openai.com/)
- [IBM Watson](https://www.ibm.com/watson)
- [CognitiveClass.ai](https://cognitiveclass.ai/)
- [IBM Developer Skills Network](https://developer.ibm.com/skills/)

---