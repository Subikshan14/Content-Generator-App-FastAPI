# Basic FastAPI Project

## Setup on Windows

Install Python from <https://www.python.org/downloads/> if it is not already installed, and enable the option to add Python to PATH.

Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install FastAPI and Uvicorn:

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Run the app

Install Ollama from <https://ollama.com/download/windows>, then download the free Llama model:

```powershell
ollama pull llama3.2
```

The API defaults to the local Ollama URL `http://localhost:11434`. To use a different Ollama server, set `OLLAMA_BASE_URL` in the environment where FastAPI runs. In Vercel, add `OLLAMA_BASE_URL` in the project's environment variables; set it to the reachable Ollama server base URL, without `/api/generate`.

Start Ollama if it is not already running, then start the API:

```powershell
uvicorn main:app --reload
```

Open <http://127.0.0.1:8000/docs> to try the API. Send a `POST` request to `/generate` with a prompt:

```json
{
  "prompt": "Write a short welcome message."
}
```

The endpoint returns the generated text. You can optionally pass a different Ollama model in the `model` field, as long as it has been downloaded.
