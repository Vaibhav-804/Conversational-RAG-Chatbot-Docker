# Conversational RAG Chatbot

A containerized RAG chatbot for conversational Q&A over PDF documents, built with LangChain, Streamlit, and Groq's Llama 3.3 70B.

## Features

- Multi-PDF document upload and processing
- Conversational chat with full history support
- Vector similarity search using ChromaDB
- Dockerized for easy deployment
- Powered by Llama 3.3 70B via Groq API

## Quick Start

### Prerequisites

- Docker installed
- [Groq API key](https://console.groq.com/)
- [HuggingFace token](https://huggingface.co/settings/tokens)

### Installation

```bash
# Clone repository
git clone https://github.com/Vaibhav-804/Conversational-RAG-Chatbot-Docker.git
cd Conversational-RAG-Chatbot-Docker

# Setup environment variables
cp .env.example .env
# Edit .env with your API keys

# Build and run
docker build -t conversational-rag .
docker run -d --name rag-app -p 8501:8501 --env-file .env conversational-rag

# Access application
open http://localhost:8501
```

## Usage

1. Enter your Groq API key in the interface
2. Upload one or more PDF documents
3. Ask questions about your documents
4. Engage in follow-up conversations with full context

## Tech Stack

- **LLM**: Llama 3.3 70B (Groq)
- **Framework**: LangChain 0.3.20
- **Embeddings**: HuggingFace sentence-transformers
- **Vector Store**: ChromaDB
- **UI**: Streamlit 1.28.0
- **Container**: Docker

## Project Structure

```
├── conversational_rag.py    # Main application
├── Dockerfile               # Container configuration
├── requirements.txt         # Dependencies
├── .env.example            # Environment template
└── .dockerignore           # Build exclusions
```

## Configuration

Required environment variables:

```env
GROQ_API_KEY=your_groq_api_key
HF_TOKEN=your_huggingface_token
```

## Development

Run locally without Docker:

```bash
pip install -r requirements.txt
export GROQ_API_KEY=your_key
export HF_TOKEN=your_token
streamlit run conversational_rag.py
```

## License

MIT License

## Author

**Vaibhav Goel**  
[GitHub](https://github.com/Vaibhav-804) • [LinkedIn](https://linkedin.com/in/vaibhav-goel-804)
