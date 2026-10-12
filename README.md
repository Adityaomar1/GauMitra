# GauMitra

GauMitra is a Flask-based cattle breed recognition project. It uses a trained
ResNet-50 model to identify cattle breeds from images and shows basic breed
information. It also has a Gemini chatbot for cattle-related questions.

## Features

- Cattle breed prediction from an image
- Confidence score and breed details
- SQLite database for breed information
- Gemini chatbot with optional image input

## Technologies

Python, Flask, PyTorch, Torchvision, Pillow, SQLite, HTML, CSS, JavaScript,
and Google Gemini API.

## Setup

Use Python 3.11 or later.

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Linux/macOS:

```bash
source .venv/bin/activate
python -m pip install -r requirements.txt
```

The project needs these files in the main folder:

```text
final_resnet50_balanced.pth
cows.db
```

If the database needs to be created again:

```bash
python createdb.py
```

## Gemini API key

Create a `.env` file in the project folder:

```env
GEMINI_API_KEY=your_api_key_here
```

The key is only required for the chatbot. Do not share or commit this file.

## Run

```bash
python app.py
```

Open the website at:

```text
http://127.0.0.1:5000/
```

The prediction page is available at:

```text
http://127.0.0.1:5000/predict_page
```

Upload a cattle image and click **Predict**. The chatbot can be opened from
the home or prediction page.

## Main API routes

- `POST /predict` - predicts a breed from an uploaded image.
- `POST /chatbot` - sends a text message and optional image to the chatbot.

## Limitations

The project requires the correct model file. Chatbot replies require a valid
Gemini API key and internet connection. Chatbot advice should not replace a
veterinarian.

There is currently no license file in the project.
