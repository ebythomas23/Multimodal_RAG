# Multimodal RAG Pipeline with Vector Index Comparison

This project implements a complete Retrieval-Augmented Generation (RAG) pipeline using a 150+ page PDF document containing text, images, and tables. The pipeline covers everything from preprocessing and semantic chunking to vector embedding, multi-index storage, retriever benchmarking, LLM integration, and DOCX export.

It demonstrates practical experience with LangChain, vector databases, OpenAI embeddings, Google Gemini, and document processing.

---

## Tech Stack

### Core Libraries
- **LangChain** – used to orchestrate document loaders, chunkers, retrievers, prompts, and LLMs  
- **python-docx** – for formatting and exporting responses as Word documents  
- **Tesseract OCR** – integrated through LangChain to extract text from images in PDFs  

### Embeddings and Language Models
- **OpenAI** – used `text-embedding-3-large` to generate dense semantic vectors  
- **Gemini 1.5 Flash** – accessed via `langchain-google-genai` for generating final answers  

### Vector Database and Indexing
- **Milvus on Zilliz Cloud** – used to store and query embeddings  
  - Configured with three index types:  
    - FLAT  
    - HNSW  
    - IVF_FLAT  

### Development Environment
- Python 3.13  
- Jupyter Notebook or VSCode with interactive Python  
- `.env` for managing API keys and connection credentials  

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/multimodal-rag.git
cd multimodal-rag


### 2. Set Up the Environment

```bash
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
pip install -r requirements.txt

### 3. Add API Keys

Create a `.env` file in the root directory with the following:

```ini
LANGCHAIN_API_KEY="your_key"
OPENAI_API_KEY="your_key"
LANGCHAIN_PROJECT="your_project_name"
ZILLIZ_CLOUD_API_KEY="your_key"
ZILLIZ_CLOUD_URI="your_uri"
GOOGLE_API_KEY="your_key"

Use `.env_example` as a template.

### Notes

- Make sure your OpenAI key has access to `text-embedding-3-large`
- Gemini model access is handled via `langchain-google-genai` and uses browser-based login

## Project Structure

```yaml
.
├── code.ipynb              # Full RAG pipeline notebook
├── data/
│   └── 2507.13334v1.pdf    # Input PDF
├── output/
│   └── rag_output.docx     # LLM–generated answer
├── .env_example            # Sample environment configuration
├── requirements.txt        # Python dependencies
└── README.md


