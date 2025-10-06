# 📚 AI-Powered IT Book Recommender

This repository contains an AI book recommendation system integrating:

- **Groq API** (Llama 70B) for intelligent suggestion and explanation  
- **Streamlit** for a web interface  
- **ngrok** for exposing the Streamlit app publicly  
- A dataset of **IT / technical books** with metadata (title, description, pages, price, etc.)

---

## 🧩 Table of Contents

1. [Features](#features)  
2. [Dataset](#dataset)  
3. [Getting Started](#getting-started)  
   - Prerequisites  
   - Clone & Setup  
   - API Keys & Secrets  
   - Running Locally / in Colab  
4. [Usage](#usage)  
5. [Project Structure](#project-structure)  
6. [Security & Best Practices](#security--best-practices)  
7. [Future Improvements](#future-improvements)  
8. [License](#license)

---

## ✅ Features

- User-friendly web UI (Streamlit) for entering interests / queries  
- AI-driven recommendations from Groq LLM  
- Contextual understanding — LLM reasons about dataset metadata & user input  
- Uses metadata like price, description, pages, type to guide recommendation  
- Live deployment via `ngrok` so you can demo from Colab / remote environment

---

## 📚 Dataset

The dataset (`data/IT_Books.csv`) should include columns such as:

| Column | Description |
|---|---|
| `Rating` | User rating (average) |
| `Reviews` | Number of reviews |
| `Book_title` | Title of the book |
| `Description` | Short summary or blurb |
| `Number_Of_Pages` | Page count |
| `Type` | Format / edition (e.g. Hardcover, Kindle, Paperback) |
| `Price` | Price (USD or relevant currency) |

> **Note:** Ensure data is cleaned, missing descriptions removed, and numeric columns are parsed correctly.

---

## 🛠️ Getting Started

### 🔍 Prerequisites

- Python 3.8+  
- Access to the **Groq API** (valid API key)  
- `ngrok` account / auth token for public tunneling  
- Web browser to access the Streamlit UI  

🔐 API Keys & Secrets
Groq API Key
Obtain it from your Groq dashboard
Don’t commit it to version control
In production, use Google Secret Manager or environment variables
ngrok Auth Token
From your ngrok dashboard
Run ngrok config add-authtoken <YOUR_TOKEN>
🏃 Running Locally / in Colab

🧑‍💻 Usage
Open the web interface
Input your interest / query (e.g. “machine learning for beginners”)
Click “Get Recommendations”
The LLM will output 3 recommended books with short reasoning
You can extend it to:
Filter by price range
Filter by book type
Search by title / author keyword
Show similarity scores or metadata

📁 Project Structure
AI-Book-Recommender/
│
├── app.py                 # Main Streamlit + Groq integration
├── requirements.txt
├── README.md
├── .gitignore
└── data/
    └── IT_Books.csv       # Dataset file

🔐 Security & Best Practices

Never hardcode your Groq / ngrok tokens in public files
Use environment variables or secret managers
Rotate your keys regularly
For PHI / sensitive data, use de-identification and contractual safeguards (e.g. BAA)
Log only non-sensitive metadata
Add error handling in case Groq API is unavailable

🚀 Future Improvements
Use embeddings + retrieval + LLM hybrids (retrieve relevant books then ask LLM to re-rank)
Add user profiles / preferences (past reads, ratings)
Use vector DB (Chroma, FAISS) for scalable retrieval
Add filters (genre, price, page count) in UI
Support explanations / citation of passages
Deploy to a proper server / cloud host (AWS, GCP) instead of Colab

📜 License
This project is licensed under the MIT License — see LICENSE
 for details.
Feel free to reuse, adapt, and build on it for research or personal projects.
