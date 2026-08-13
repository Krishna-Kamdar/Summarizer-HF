# Dialogue Summarizer (T5 + FastAPI)

A lightweight web application that uses a fine-tuned **T5-small** model to generate concise summaries from chat dialogues or text transcripts. The project combines a Hugging Face transformer model with a minimal **FastAPI** backend and a clean HTML/CSS/JS frontend.

## 🚀 Tech Stack

* **Machine Learning:** Python, PyTorch, Hugging Face Transformers (`T5-small`, `Trainer`), Pandas, RegEx
* **Backend:** FastAPI, Uvicorn, Jinja2
* **Frontend:** HTML5, CSS3, Vanilla JavaScript (Fetch API)

---

## 📁 Project Structure

```text
├── saved_summary_model/    # Directory containing the fine-tuned T5 model and tokenizer
├── static/
│   ├── style.css           # Custom styling for the web interface
│   └── script.js           # Frontend logic handling async API requests
├── templates/              # (or root) HTML templates
│   └── index.html          # Main web interface view
├── main.py                 # FastAPI server and inference script
└── README.md

⚙️ How It Works
Model Fine-Tuning: The model leverages Transfer Learning, taking a pre-trained t5-small model (which already understands English grammar and syntax) and fine-tuning it on a randomized subset of the SAMSum dataset for dialogue summarization.

Backend API (main.py): FastAPI loads the saved model into memory (leveraging GPU acceleration via CUDA or MPS if available) and exposes a /summarize/ POST endpoint.

Frontend Interface: Users can paste any conversation or text block into the web UI, click Summarize, and the JavaScript fetch API sends the text to the backend without requiring a full page reload.

🛠️ Getting Started & Installation
### 1. Clone the Repository

```bash
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

### 2. Install Dependencies
Make sure you have Python installed, then install the required libraries:

```bash
pip install fastapi uvicorn transformers torch pandas pydantic jinja2

### 3. Ensure Model Files are Present
Make sure your fine-tuned model files (model.safetensors/pytorch_model.bin, config.json, tokenizer files) are placed inside a folder named saved_summary_model/ in the root directory.

### 4. Run the FastAPI Server
Start the server using Uvicorn:

```bash
uvicorn main:app --reload

### 5. Access the App
Open your web browser and navigate to:
[http://127.0.0.1:8000](http://127.0.0.1:8000)
