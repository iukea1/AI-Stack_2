## AI Stack with Ollama, Open-WebUI, SearxNG, Whisper, and LibreTranslate

This project sets up a comprehensive AI stack using Docker Compose, featuring:

* **Ollama:** A powerful, privacy-focused large language model (LLM) server.
* **Open-WebUI:** A user-friendly interface for interacting with Ollama and performing various AI tasks.
* **SearxNG:** A privacy-respecting metasearch engine, enabling web search capabilities within Open-WebUI.
* **Whisper:** A robust speech-to-text engine for transcribing audio files.
* **LibreTranslate:** An open-source machine translation engine for real-time language translation.
* **MongoDB:** A NoSQL database for storing Whisper transcriptions and other data.

This stack provides a robust foundation for building AI-powered applications with a focus on privacy, customization, and extensibility.

### Features

- **Conversational AI:** Engage in natural language conversations with powerful LLMs through Ollama and Open-WebUI.
- **Web Search Integration:** Enhance your AI interactions with relevant web search results powered by SearxNG.
- **Speech-to-Text Transcription:** Easily transcribe audio files with accurate and efficient speech recognition.
- **Real-time Language Translation:** Seamlessly translate text between various languages using LibreTranslate.
- **Customizable and Extensible:** Tailor the stack to your specific needs by leveraging the flexibility of Docker Compose.

### Requirements

- Docker
- Docker Compose
- NVIDIA GPU (recommended for optimal performance)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/ai-stack.git
   cd ai-stack
   ```
2. Create a `.env` file based on `.env.example`, updating the values as needed.
3. (Optional) Adjust the configurations in `compose.yaml` to your preferences.
4. Start the stack:
   ```bash
   docker-compose up -d
   ```

### Usage

Once the stack is running:

- Access Ollama's API at `http://localhost:11434`.
- Access Open-WebUI at `http://localhost:8080`.
- Access SearxNG at `http://localhost:8081`.
- Upload audio files for transcription through Whisper's interface.
- Utilize LibreTranslate's API for language translation.

### Configuration

- Customize the services and their settings by modifying the `compose.yaml` file.
- Adjust environment variables in the `.env` file to modify application behavior.
- Refer to the official documentation of each component for detailed configuration options:
  - [Ollama](https://github.com/ollama-ai/ollama)
  - [Open-WebUI](https://github.com/open-webui/open-webui)
  - [SearxNG](https://github.com/searxng/searxng)
  - [Whisper](https://github.com/openai/whisper)
  - [LibreTranslate](https://github.com/LibreTranslate/LibreTranslate)

### Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or a pull request.

### License

This project is licensed under the MIT License.
