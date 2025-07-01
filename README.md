# 🛡️ Cybersecurity RAG Chatbot

A secure and intelligent chatbot for answering cybersecurity-related questions using Retrieval-Augmented Generation (RAG). It allows users to upload PDF/TXT files (e.g., security policies, legal documents, training guides), then ask questions and get accurate, contextual responses — with memory!

---

## 🚀 Features

- 📄 PDF & TXT Upload
- 🔍 Document Chunking & Embedding
- 🧠 Vector DB using Chroma
- 🤖 RAG with optional Chat History
- 💬 Streamlit Chat UI (Styled for Cybersecurity)
- 🔁 Retriever-Reranker pipeline
- 🧠 Memory-aware conversation (LangChain)

---

## 📦 Tech Stack

| Component              | Library/Service         |
|------------------------|-------------------------|
| Vector DB              | `ChromaDB`              |
| Embeddings             | `sentence-transformers` |
| LLM                    | `Groq` |
| RAG Logic              | `LangChain`             |
| UI                     | `Streamlit`             |
| File Parsing           | `PyPDF`, `LangChain`    |
| Memory + Chat History  | `LangChain` Message Store |
| Re-ranking             | `Cohere` |

---

## 📁 Folder Structure

```bash
Cybersecurity-RAG-Chatbot/
├── app.py                     # Streamlit frontend UI
├── utils.py                   # Core utilities: load docs, chunking, embedding
├── Cybersecurity RAG.ipynb    # Notebook version for experimentation
├── requirements.txt           # All required Python packages
├── .env.example               # Sample environment variables
├── README.md                  # Project documentation (this file)
└── data/
    └── Introduction to Cybersecurity.pdf             # Example input document
```

---

## 🧠 How It Works

1. **Upload File**  
   → PDF/TXT files are parsed and chunked.

2. **Embed Chunks**  
   → Each chunk is transformed into vector embeddings using `sentence-transformers`.

3. **Store in Vector DB**  
   → Embeddings are stored in ChromaDB for retrieval.

4. **Ask a Question**  
   → The user types a cybersecurity-related question.

5. **Retriever + (Optional) Reranker**  
   → Top-k most relevant chunks are fetched based on similarity. Reranker (e.g. cross-encoder) improves quality.

6. **RAG Generation**  
   → Retrieved chunks + question are passed to the LLM to generate a grounded answer.

7. **Chat Memory**  
   → Keeps track of previous questions/answers to allow contextual conversation.

---

## 🛠️ Setup & Installation

```bash
# Clone the repository
git clone https://github.com/omarsabri125/Cyber-Security-RAG-System.git
cd Cyber-Security-RAG-System

# Install dependencies
pip install -r requirements.txt

# (Optional) Add your API keys
cp .env.example .env
# Then edit `.env` to add Hugging Face / Groq / OpenAI keys

# Run the app
streamlit run app.py
```

---

## 🧪 Example Prompt

> **Question:**  
> *What are the key elements of a secure password policy in the uploaded document?*

> **Answer (Generated):**  
> According to the uploaded cybersecurity manual, a secure password policy should include minimum length, special characters, expiration rules, and multi-factor authentication integration.

---

## 🔐 Environment Variables (`.env`)

```env
HUGGINGFACEHUB_API_TOKEN=your_hf_token
COHERE_API_KEY=your_cohere_key
GROQ_API_KEY=your_groq_key
```

---

## 📌 Use Cases

- Cybersecurity compliance assistants for enterprises
- Smart document Q&A from uploaded training manuals
- Cyberlaw or legal document interpreters
- Privacy policy summarization bots

