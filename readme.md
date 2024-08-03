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

## Requirements

- **Docker:** Install and configure Docker for your operating system from [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)
- **Docker Compose:** Install Docker Compose: [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)
- **NVIDIA GPU (Recommended):** For optimal performance, especially with LLMs, a dedicated NVIDIA GPU is strongly recommended.
    - Install the **NVIDIA Container Toolkit:**  [https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)

## Installation & Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/ai-stack.git
   cd ai-stack
   ```

2. **Configure Environment Variables:**
   - Create a `.env` file by copying the example:
     ```bash
     cp .env.example .env
     ```
   - **Edit `.env`:** 
      - Update database credentials (`DB_USER`, `DB_PASS`).
      - Set `WHISHPER_HOST` (e.g., `http://your-domain.com` or your server's IP address if hosting remotely).
      - (Optional) Modify other settings like `LT_LOAD_ONLY` to pre-load specific languages for LibreTranslate.

3. **Prepare Data Directories:** 
    - Create directories for persistent data (these will be mounted as volumes):
        ```bash
        mkdir -p ollama_data open-webui_data searxng_data mongo_data mongo_logs libretranslate_data libretranslate_cache whisper_uploads whisper_logs whisper_models
        ```
    - Set appropriate ownership for the directories:
       ```bash
       sudo chown -R $UID:$GID ./ollama_data ./open-webui_data ./searxng_data ./mongo_data ./mongo_logs ./libretranslate_data ./libretranslate_cache ./whisper_uploads ./whisper_logs ./whisper_models
       ```

4. **Start the Stack:**
   ```bash
   docker-compose up -d
   ```

## Usage

Once the stack is running:

- **Ollama API:**  `http://localhost:11434`
- **Open-WebUI:** `http://localhost:8080`
- **SearxNG:** `http://localhost:8081` 
- **Whisper:**  Upload audio files for transcription through the Open-WebUI interface. 

## Customization

- **`docker-compose.yaml`:** Modify service configurations, ports, resource limits, and more.
- **`.env` File:** Adjust environment variables to fine-tune application behavior.
- **Dockerfiles:** (Optional) Customize individual service configurations further if needed.

## Troubleshooting

- **Logs:** Use `docker-compose logs -f <service_name>` to view logs from specific services.
- **Inspect:** Use `docker inspect <container_name>` to get detailed information about a container.
- **Restart:** If you encounter issues