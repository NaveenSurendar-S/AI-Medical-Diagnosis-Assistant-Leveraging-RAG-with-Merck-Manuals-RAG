# Healthcare Decision Support System with RAG

A Retrieval-Augmented Generation (RAG) project for evidence-based healthcare decision support using medical knowledge from the Merck Manuals. This project demonstrates how a large language model can answer clinical and medical questions more reliably by retrieving relevant context from a trusted medical source before generating a response.

## Overview

This project combines:

- PDF document ingestion from a medical reference source
- Text chunking and preprocessing
- Embedding generation using sentence-transformers
- Vector storage with Chroma
- Retrieval of the most relevant document chunks
- Response generation using a local LLaMA-based language model
- Comparison between base prompt-engineering responses and RAG-based answers

The goal is to improve groundedness, reduce hallucination risk, and support healthcare professionals with context-based medical answers.

## Why this project matters

Medical information is large, dynamic, and often difficult to access quickly. Traditional LLMs may answer confidently without authoritative sources. This RAG system addresses that by grounding responses in retrieved medical text, helping provide more trustworthy and evidence-based answers.

## Project structure

- `Healthcare_Decision__Support_System_RAG.ipynb` — main notebook containing the full workflow
- `README.md` — project overview and usage instructions

## Tech stack

- Python
- Jupyter Notebook
- LangChain
- ChromaDB
- SentenceTransformers
- PyMuPDF
- Hugging Face Hub
- llama.cpp / LLaMA model runtime
- Pandas

## Workflow

1. Load the medical PDF document
2. Split the document into smaller chunks
3. Create embeddings for each chunk
4. Store the embeddings in a vector database
5. Retrieve the most relevant chunks for a user question
6. Pass the retrieved context to the LLM
7. Generate a grounded, evidence-based medical answer
8. Evaluate the quality of prompt-engineered vs RAG responses

## Example use cases

- Clinical question answering
- Diagnostic support
- Evidence-based medical information retrieval
- Education and research assistant for healthcare topics

## Setup

### Requirements

- Python 3.10+
- Jupyter Notebook or Google Colab
- Internet access for downloading the model and dependencies
- Sufficient RAM/GPU resources for local LLM inference

### Install dependencies

```bash
pip install -U langchain langchain-community langchain-huggingface \
  sentence-transformers chromadb huggingface_hub transformers \
  langchain-text-splitters langchain-chroma pymupdf
```

For the local LLaMA runtime:

```bash
pip install llama-cpp-python
```

## Running the project

1. Open the notebook: `Healthcare_Decision__Support_System_RAG.ipynb`
2. Ensure the medical PDF file is available in the expected location or update the file path in the notebook
3. Run the notebook cells in order
4. Wait for the model download and embedding setup to complete
5. Ask a medical question to test the RAG pipeline

## Important notes

- This is a research and prototype project, not a clinical decision-making system
- Always validate medical answers with qualified healthcare professionals
- The retrieved context improves grounding, but source quality and model limitations still matter
- Use this project as a demonstration of RAG for healthcare, not as a replacement for professional medical advice

## Example questions tested in this project

- What is the protocol for managing sepsis in a critical care unit?
- What are the common symptoms of appendicitis and how is it treated?
- What are the causes and treatments for patchy hair loss?
- What treatments are recommended for brain injury-related impairment?

## Limitations

- The knowledge base depends on the quality and scope of the medical PDF
- Some responses may still require domain review
- Local LLM performance depends on hardware capability
- Retrieval quality depends on chunk size, embedding model, and similarity search settings

## Acknowledgements

- Merck Manuals for medical reference content
- LangChain and Chroma for retrieval and vector database tooling
- Hugging Face for open-source model access
- The open-source AI and ML community

## Future improvements

- Add a web interface for easier interaction
- Support more medical document sources
- Improve evaluation metrics and clinical validation
- Add API-based access for real-time querying
- Package the project as a reusable application

## Final note

This project demonstrates how RAG can make AI-driven healthcare support more grounded, explainable, and useful. It is a solid foundation for building a more robust clinical decision support tool with proper validation and domain expertise.
