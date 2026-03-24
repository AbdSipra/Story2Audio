# Story2Audio

Story2Audio is a text-to-audio application built around a gRPC backend and a Gradio frontend. It converts user-provided story text into narrated audio using a text-to-speech pipeline.

## Stack

- Python
- gRPC
- Gradio
- Parler TTS / Transformers / Torch
- Docker

## Project Structure

- `backend/` contains the gRPC service, model wrappers, and tests.
- `frontend/` contains the Gradio app.
- `docker/` contains container and compose files.
- `deployment/` contains a deployment manifest.
- `architecture.png` contains the system diagram.

## Quick Start

```bash
pip install -r requirements.txt
python -m backend.app.server
python frontend/app.py
```

The backend listens on port `50051` and the Gradio frontend runs on port `7860`.
