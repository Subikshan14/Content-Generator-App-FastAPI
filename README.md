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

```powershell
uvicorn main:app --reload
```

Open <http://127.0.0.1:8000> to view the app, or <http://127.0.0.1:8000/docs> for the interactive API documentation.
