# Voice Assistant with OpenAI's GPT-3 and IBM Watson

![cognitiveclass.ai logo](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-Developer-Skills-Network-ML0101EN-SkillsNetwork/labs/FinalModule_Coursera/images/logo-cc.png)

This project guides you through building a full-stack voice assistant. The assistant takes voice input, converts it to text, gets an intelligent response from OpenAI's GPT-3 model, converts the response back to speech, and plays it for the user.

The application features a responsive frontend built with HTML, CSS, and JavaScript, and a reliable backend powered by Python and Flask.

Click here to play with a demo of the final application that you will create! *(Demo link from original course material)*

---

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [How It Works](#how-it-works)
- [Screenshots](#screenshots)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Learning Objectives](#learning-objectives)
- [Acknowledgements](#acknowledgements)

---

## Features

- **🎤 Voice Interaction:** Speak to the assistant and hear its responses.
- **🧠 Intelligent Responses:** Powered by OpenAI's `gpt-3.5-turbo` model for natural and coherent conversations.
- **🗣️ High-Quality Speech Services:** Utilizes IBM Watson for fast and accurate Speech-to-Text and Text-to-Speech conversion.
- **🌐 Responsive Web Interface:** A clean and modern user interface built with HTML, CSS, and JavaScript.
- **🎨 Light & Dark Modes:** User-friendly theme switching for better viewing comfort.
- **📦 Containerized:** Comes with a `Dockerfile` for easy setup and consistent deployment across environments.
- **🐍 Python Backend:** Built on the lightweight and powerful Flask web framework.

---

## Tech Stack

- **Backend:** Python, Flask
- **Frontend:** HTML, CSS, JavaScript, JQuery, Bootstrap, Font Awesome
- **AI Services:**
    - OpenAI API (`gpt-3.5-turbo`)
    - IBM Watson Speech to Text
    - IBM Watson Text to Speech
- **Containerization:** Docker

---

## How It Works

The application follows a simple but powerful architecture:

1.  **Frontend (JavaScript):** Captures microphone audio when the user clicks the record button.
2.  **Speech-to-Text:** The audio data is sent to the Flask backend's `/speech-to-text` endpoint. The backend forwards this to the **IBM Watson Speech-to-Text API**.
3.  **User Prompt:** The transcribed text is returned to the frontend and displayed as the user's message.
4.  **Process Prompt:** The frontend sends the transcribed text to the backend's `/process-message` endpoint.
5.  **OpenAI GPT-3:** The backend sends the text prompt to the **OpenAI API**, asking it to act as a personal assistant.
6.  **Text-to-Speech:** The text response from OpenAI is sent to the **IBM Watson Text-to-Speech API** to be converted into audio.
7.  **Final Response:** The backend sends the text response and the synthesized audio (as a base64 string) back to the frontend.
8.  **Playback:** The frontend displays the assistant's text response and automatically plays the audio.

---

## Screenshots

<p align="center">
  <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-Developer-Skills-Network-GPXX0ZN0EN/light-mode.png" alt="Light Mode Screenshot" width="45%">
     
  <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-Developer-Skills-Network-GPXX0ZN0EN/dark-mode.png" alt="Dark Mode Screenshot" width="45%">
</p>

---

## Prerequisites

- **Docker:** The application is designed to run in a Docker container. Make sure you have Docker installed.
- **Git:** To clone the starter repository.
- **API Keys:**
    > **Note:** This project was originally a guided project for the [CognitiveClass.ai](https://cognitiveclass.ai/) platform, which provides pre-configured IBM Watson services. If running this project outside that environment, you will need to:
    > 1.  Create an **OpenAI** account and get an API key.
    > 2.  Create an **IBM Cloud** account and provision instances of **Speech to Text** and **Text to Speech** to get their service URLs and API keys.

---

## Getting Started

Follow these steps to set up and run the project.

### 1. Clone the Repository

Clone the outline project from the IBM Developer Skills Network GitHub repository.

```bash
git clone https://github.com/ibm-developer-skills-network/bkrva-chatapp-with-voice-and-openai-outline.git
mv bkrva-chatapp-with-voice-and-openai-outline chatapp-with-voice-and-openai-outline
cd chatapp-with-voice-and-openai-outline 

### 2. Configure the Services

You need to tell the application where to find the Watson and OpenAI services. All changes are made in the worker.py file.

A. Configure IBM Watson Speech-to-Text
In worker.py, locate the speech_to_text function and update the base_url variable with your Watson Speech-to-Text service URL.

# worker.py

def speech_to_text(audio_binary):
    # Set up Watson Speech-to-Text HTTP Api url
    base_url = 'https://sn-watson-stt.labs.skills.network' # <-- REPLACE WITH YOUR URL
    api_url = base_url + '/speech-to-text/api/v1/recognize'
    # ...

B. Configure IBM Watson Text-to-Speech

In worker.py, locate the text_to_speech function and update the base_url variable with your Watson Text-to-Speech service URL.

# worker.py

def text_to_speech(text, voice=""):
    # Set up Watson Text-to-Speech HTTP Api url
    base_url = 'https://sn-watson-tts.labs.skills.network' # <-- REPLACE WITH YOUR URL
    api_url = base_url + '/text-to-speech/api/v1/synthesize?output=output_text.wav'
    # ...

C. Configure OpenAI
The outline code uses a pre-configured openai_client. You will need to ensure it is initialized with your API key, typically via an environment variable.

### 3. Build and Run the Application with Docker

The provided Dockerfile packages the application and all its dependencies.
First, run the prerequisite commands if you are in the lab environment (this step may not be necessary for local setups).

mkdir -p /home/project/chatapp-with-voice-and-openai-outline/certs/
cp /usr/local/share/ca-certificates/rootCA.crt /home/project/chatapp-with-voice-and-openai-outline/certs/

Now, build the Docker image and run the container.

# Build the Docker image

docker build . -t voice-chatapp-powered-by-openai

# Run the container, mapping port 8000

docker run -p 8000:8000 voice-chatapp-powered-by-openai

Note: If you make changes to the code, you will need to stop the container (Ctrl+C), rebuild the image, and run it again.

### 4. Test Your Assistant

Open your web browser and navigate to http://localhost:8000.

You can now interact with your voice assistant! Try typing a message or clicking the microphone icon to speak.