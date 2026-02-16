# Open Notebook + SurrealDB (with local Ollama): Fully Local Open Source Alternative to NotebookLM

This repo provides a reproducible Docker Compose stack for running **Open Notebook** with **SurrealDB**, while using **Ollama installed locally**.

## Requirements
- Docker & Docker Compose
- Ollama installed on your host machine
- Ollama API running (`ollama serve`)

## Setup
1. Clone the repo:
   ```bash
   git clone https://github.com/ghassenbenali96/OpenNotebook-Local.git
   cd OpenNotebook-Local-main
   ```
2. Create .env with a secure encryption key:
   ```bash
   openssl rand -hex 32 > .env
   ```
3. Start Ollama locally:
   ```bash
   ollama serve
   ```
4. Launch the stack:
   ```bash
   docker compose up -d
   ```
## Services
- Open Notebook UI → http://localhost:8502
- Open Notebook API → http://localhost:5055
- SurrealDB → http://localhost:8000
- Ollama API (local) → http://localhost:11434

## Model Configuration
Default models are set in docker-compose.yml:
- Chat → llama2
- Embedding → mxbai-embed-large
- Transformation → llama2

You can override these in the Open Notebook settings UI once the app is running.

## Data Persistence
- notebook_data/ → Open Notebook data
- surreal_data/ → SurrealDB RocksDB storage
