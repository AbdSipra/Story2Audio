# Story2Audio

Story2Audio is a text-to-speech project that converts story text into spoken audio through a service-based architecture.

The project uses a Python gRPC backend for audio generation and a Gradio frontend for interaction. The current main pipeline synthesizes text sentence by sentence using the `parler-tts/parler-tts-mini-jenny-30H` model and returns the combined WAV audio to the frontend.

## Features

- gRPC-based backend API for audio generation
- Gradio web interface for entering story text and playing generated audio
- Sentence-level audio generation and concatenation
- Input validation for empty, invalid, or over-length requests
- Docker configuration for easier deployment
- Basic backend test coverage

## Tech Stack

- Python
- gRPC
- Gradio
- Hugging Face Transformers
- Parler TTS
- NumPy
- SoundFile

## Project Structure

- `backend/app/server.py` - gRPC server
- `backend/model/tts_model.py` - TTS model wrapper
- `backend/protos/audio.proto` - service contract
- `frontend/app.py` - Gradio UI
- `docker/` - container configuration
- `architecture.png` - system architecture diagram

## How It Works

1. The user enters story text in the Gradio interface.
2. The frontend sends the request to the gRPC backend.
3. The backend validates the input and splits it into sentences.
4. Each sentence is converted into speech.
5. The audio segments are concatenated and returned as a WAV response.

## Run Locally

```bash
pip install -r requirements.txt
python backend/app/server.py
python frontend/app.py
```

Backend runs on port `50051` and the frontend runs on port `7860`.

## Notes

- The repo also contains an experimental LLM narration-style helper, but the main runnable flow is the text-to-speech pipeline described above.
- The current project is a working prototype focused on architecture and generation flow rather than large-scale production deployment.
