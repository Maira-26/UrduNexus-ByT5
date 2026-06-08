#  UrduNexus: AI Transliteration Engine

UrduNexus is a high-speed, AI-powered system that seamlessly converts Roman Urdu text into native Urdu script. Built using a fine-tuned ByT5 model, it features a self-contained architecture hosted on Google Colab, completely bypassing local hardware constraints and network blocks.

##  Key Features
* **Real-Time Transliteration:** Converts Roman Urdu to native script instantly using a customized `google/byt5-small` model.
* **Smart Chunking:** Automatically handles long paragraphs without hitting token limits.
* **Voice Integration:** Built-in Text-to-Speech (TTS) using Microsoft `edge-tts` (ur-PK-UzmaNeural voice).
* **Self-Contained Architecture:** The Python backend dynamically generates the HTML/CSS/JS frontend on the fly—no manual file uploads required.
* **Unblockable Tunneling:** Utilizes `bore.pub` to expose the local Colab FastAPI server to the public web securely.
* **Glassmorphism UI:** A beautiful, responsive, and modern web interface.

##  Tech Stack
* **Machine Learning:** PyTorch, Hugging Face Transformers (`Maira26/UrduNexus-ByT5`)
* **Backend:** Python, FastAPI, Uvicorn
* **Frontend:** HTML5, CSS3, Vanilla JavaScript
* **Deployment:** Google Colab T4 GPU, Bore.pub Tunneling

##  How to Run (1-Click Setup)
Because this project is designed to run on free cloud GPUs, installation is entirely automated.

1. Open the `UrduNexus_Demo.ipynb` notebook in Google Colab.
2. Go to **Runtime > Change runtime type** and ensure **T4 GPU** is selected.
3. Click **Run All** (or press `Ctrl + F9`).
4. Wait 1-2 minutes for the system to install dependencies, load the model into VRAM, and spin up the tunnel.
5. Click the public `bore.pub` link printed at the bottom of the cell to access the live web app!

##  System Architecture
1. **Frontend:** User types Roman Urdu into the browser UI. JavaScript sends a `POST` request to the backend.
2. **Backend Engine:** FastAPI receives the text, chunks it into <180 character segments, and feeds it to the ByT5 model via PyTorch.
3. **Audio Generation:** The native Urdu output is hashed and converted to an `.mp3` using `edge-tts`.
4. **Response:** The system returns the Urdu text and the relative path to the audio file, which the browser immediately displays and loads into the hidden audio player.

##  Demonstration

<img width="1917" height="865" alt="image" src="https://github.com/user-attachments/assets/02e8052f-d21e-4627-b182-e0e92966fbdb" />


---

