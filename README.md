# Intelligent Document Q&A System

A local RAG (Retrieval-Augmented Generation) system that lets you ask questions about your documents and get AI-powered answers.

## What It Does

Upload a PDF, Word document, or text file and ask questions about its content. The system will:
- Extract and chunk the text
- Create embeddings for semantic search
- Retrieve relevant passages
- Generate accurate answers using AI

## Features

- **Multi-format support**: PDF, DOCX, and TXT files
- **Semantic search**: Uses sentence transformers for intelligent retrieval
- **Local processing**: Runs entirely on your machine, no API keys needed
- **Fast vector search**: Powered by FAISS

## Requirements

```bash
pip install PyPDF2 python-docx sentence-transformers faiss-cpu transformers torch tiktoken numpy
```

## How to Use

1. Create a folder called `QnADocuments` in the project directory
2. Place your document in the folder
3. Run the notebook cells in order
4. Use `ask_question("Your question here")` to query your document

## Example

```python
ask_question("What is a deductible?")
# Output: "A deductible is the amount you pay out of pocket before your insurance coverage starts paying for a claim."
```

## Models Used

- **Embeddings**: `all-MiniLM-L6-v2` (sentence-transformers)
- **Answer Generation**: `google/flan-t5-large` (Hugging Face)
- **Vector Store**: FAISS (Facebook AI Similarity Search)

## Notes

- First run will download the AI models (~1-2GB total)
- Works best with documents under 50 pages
- Runs on CPU by default (GPU optional for faster processing)
