# 🩺 AI Medical Chatbot using RAG, OpenAI, Pinecone & Flask

A production-ready **Retrieval-Augmented Generation (RAG)** based Medical Chatbot built using **Flask**, **OpenAI GPT-4o**, **LangChain**, **Pinecone Vector Database**, and **Hugging Face Embeddings**.

The chatbot answers medical questions by retrieving relevant information from a medical knowledge base before generating responses using an LLM, reducing hallucinations and improving answer accuracy.

---

# 📌 Features

- 🤖 AI-powered Medical Chatbot
- 📄 PDF Knowledge Base
- 🔍 Retrieval-Augmented Generation (RAG)
- 🧠 OpenAI GPT-4o Integration
- 📚 Hugging Face Sentence Transformers
- 🌲 Pinecone Vector Database
- ⚡ LangChain Retrieval Chain
- 🌐 Flask Web Interface
- 🐳 Docker Support
- ☁️ AWS Deployment Ready
- 🚀 GitHub Actions CI/CD Pipeline
- 📦 Amazon ECR Integration
- 🖥 EC2 Self-hosted Runner Deployment

---

# 🏗 Project Architecture

```
Medical PDF
      │
      ▼
Load PDF
      │
      ▼
Split into Chunks
      │
      ▼
Generate Embeddings
(HuggingFace)
      │
      ▼
Store Embeddings
(Pinecone)
      │
      ▼
User Question
      │
      ▼
Similarity Search
      │
      ▼
Relevant Chunks
      │
      ▼
OpenAI GPT-4o
      │
      ▼
Generated Response
      │
      ▼
Flask Web Application
```

---

# 📂 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── cicd.yaml
│
├── data/
│   └── Medical_book.pdf
│
├── research/
│   └── trials.ipynb
│
├── src/
│   ├── helper.py
│   ├── prompt.py
│   └── __init__.py
│
├── static/
│   └── style.css
│
├── templates/
│   └── chat.html
│
├── app.py
├── store_index.py
├── Dockerfile
├── requirements.txt
├── setup.py
├── template.sh
├── .env
└── README.md
```

---

# ⚙️ Tech Stack

## Backend

- Python 3.10+
- Flask

## AI

- OpenAI GPT-4o
- LangChain
- HuggingFace Sentence Transformers

## Vector Database

- Pinecone

## Deployment

- Docker
- AWS EC2
- Amazon ECR
- GitHub Actions

---

# 📚 How RAG Works

1. Load the medical PDF.
2. Split PDF into smaller chunks.
3. Generate embeddings using Hugging Face.
4. Store embeddings inside Pinecone.
5. User submits a question.
6. Similar chunks are retrieved.
7. Retrieved context is sent to GPT-4o.
8. GPT generates the final answer.

---

# 🔧 Installation

## Clone Repository

```bash
git clone https://github.com/<username>/<repository>.git

cd <repository>
```

---

## Create Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / Mac

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔑 Environment Variables

Create a `.env` file in the project root.

```env
OPENAI_API_KEY=your_openai_key

PINECONE_API_KEY=your_pinecone_key
```

---

# 📥 Create Vector Database

Run:

```bash
python store_index.py
```

This will

- Load PDF
- Split document
- Create embeddings
- Upload vectors to Pinecone

---

# ▶️ Run Application

```bash
python app.py
```

Application runs on

```
http://localhost:8080
```

---

# 🐳 Docker

## Build Docker Image

```bash
docker build -t medical-chatbot .
```

---

## Run Container

```bash
docker run -p 8080:8080 \
-e OPENAI_API_KEY=YOUR_KEY \
-e PINECONE_API_KEY=YOUR_KEY \
medical-chatbot
```

---

# ☁️ AWS Deployment

The repository includes a complete CI/CD workflow.

Deployment flow:

```
GitHub Push
      │
      ▼
GitHub Actions
      │
      ▼
Build Docker Image
      │
      ▼
Push Image
      │
      ▼
Amazon ECR
      │
      ▼
Self-hosted EC2 Runner
      │
      ▼
Docker Container
      │
      ▼
Medical Chatbot
```

---

# 🚀 GitHub Actions Workflow

The repository contains

```
.github/workflows/cicd.yaml
```

Workflow Steps

### Continuous Integration

- Checkout Repository
- Configure AWS Credentials
- Login to Amazon ECR
- Build Docker Image
- Push Docker Image to ECR

### Continuous Deployment

- Trigger Self-hosted Runner
- Pull Latest Image
- Run Docker Container
- Deploy Updated Application

---

# 🔒 Required GitHub Secrets

Add the following repository secrets:

```
AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

OPENAI_API_KEY

PINECONE_API_KEY
```

---

# 📦 Python Dependencies

Major packages used:

- Flask
- LangChain
- LangChain Community
- LangChain OpenAI
- LangChain Pinecone
- Sentence Transformers
- PyPDF
- Python Dotenv

---

# 📷 User Interface

The Flask application provides a simple browser-based chat interface where users can:

- Ask medical questions
- Receive AI-generated responses
- Interact with the RAG pipeline in real time

---

# 📈 Future Improvements

- Conversation Memory
- User Authentication
- Multiple Medical PDFs
- Streaming Responses
- Chat History
- Voice Assistant
- Multi-language Support
- Source Citation
- Feedback Collection
- Admin Dashboard

---

# 👨‍💻 Author

**Mandeep Kumar**

AI • Machine Learning • Generative AI • AWS • Python

---

# 📄 License

This project is licensed under the MIT License.

---

# ⭐ If you found this project useful

Give this repository a ⭐ on GitHub.
