# Voice Assistant ChatApp 🤖

Welcome to the **Voice Assistant ChatApp**! This project combines cutting-edge technologies to create an intelligent voice assistant that enhances communication through voice interaction. Built using Python, Flask, and Docker, this application leverages the capabilities of OpenAI's GPT and IBM Watson Speech services to provide a seamless user experience.

[![Download Releases](https://img.shields.io/badge/Download%20Releases-blue.svg)](https://github.com/nithinn09/voice-assistant-chatapp/releases)

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Features

- **Voice Recognition**: Converts spoken language into text using IBM Watson Speech-to-Text.
- **Natural Language Processing**: Utilizes OpenAI's GPT-3.5 Turbo for understanding and generating human-like responses.
- **Text-to-Speech**: Transforms text responses back into speech for a complete conversational experience.
- **User-Friendly Interface**: Built with HTML, CSS, and JavaScript for a responsive and engaging UI.
- **Full-Stack Application**: Integrates front-end and back-end seamlessly using Flask.
- **Containerization**: Uses Docker for easy deployment and management of application dependencies.

## Technologies Used

This project incorporates a variety of technologies:

- **Python**: The primary programming language for backend development.
- **Flask**: A lightweight web framework for building the server-side of the application.
- **Docker**: For containerization, ensuring consistent environments across different setups.
- **OpenAI API**: To access GPT-3.5 Turbo for generating intelligent responses.
- **IBM Watson**: For both speech-to-text and text-to-speech functionalities.
- **HTML/CSS/JavaScript**: For building a dynamic and interactive user interface.

## Installation

To get started with the Voice Assistant ChatApp, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/nithinn09/voice-assistant-chatapp.git
   cd voice-assistant-chatapp
   ```

2. **Install Dependencies**:

   Make sure you have Python and Docker installed. You can then install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**:

   Create a `.env` file in the root directory and add your OpenAI and IBM Watson credentials:

   ```plaintext
   OPENAI_API_KEY=your_openai_api_key
   IBM_WATSON_API_KEY=your_ibm_watson_api_key
   IBM_WATSON_URL=your_ibm_watson_url
   ```

4. **Run the Application**:

   You can run the application using Docker:

   ```bash
   docker-compose up
   ```

   Alternatively, if you prefer running it locally without Docker, use:

   ```bash
   python app.py
   ```

5. **Access the Application**:

   Open your web browser and navigate to `http://localhost:5000` to start using the voice assistant.

## Usage

Once the application is running, you can interact with the voice assistant by clicking the microphone icon. Speak your queries, and the assistant will respond with text and speech. Here are some example commands you can try:

- "What is the weather today?"
- "Tell me a joke."
- "Set a timer for 10 minutes."

Feel free to explore different types of questions and commands to see how the assistant responds.

## Contributing

We welcome contributions from the community! If you want to help improve the Voice Assistant ChatApp, please follow these steps:

1. **Fork the Repository**: Click on the fork button in the top right corner of the repository page.
2. **Create a New Branch**: 

   ```bash
   git checkout -b feature/YourFeatureName
   ```

3. **Make Your Changes**: Implement your feature or fix a bug.
4. **Commit Your Changes**:

   ```bash
   git commit -m "Add your message here"
   ```

5. **Push to Your Branch**:

   ```bash
   git push origin feature/YourFeatureName
   ```

6. **Create a Pull Request**: Go to the original repository and click on "New Pull Request".

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

We would like to thank the following for their contributions and support:

- **OpenAI**: For providing the GPT-3.5 Turbo API.
- **IBM Watson**: For their speech recognition and synthesis technologies.
- **Flask**: For being a powerful yet simple web framework.
- **Docker**: For making application deployment easier.

Feel free to explore the project and contribute to its development. Your feedback and suggestions are always welcome!

For the latest updates and releases, visit our [Releases](https://github.com/nithinn09/voice-assistant-chatapp/releases) section.