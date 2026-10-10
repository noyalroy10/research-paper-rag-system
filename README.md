# Research Paper RAG System

AI-powered research paper summarization and question answering system using Large Language Models (LLMs) and Retrieval-Augmented Generation (RAG). Upload a research paper (PDF), get summaries, extract key information, and ask questions that are answered only from the paper, with page citations.

## Features
- **Four summary types:** Brief, Detailed, Bullet Points, Academic Summary (hierarchical summarization for long papers)
- **Key information extraction:** research problem, objective, methodology, dataset, algorithms, results, limitations, conclusion
- **Grounded question answering:** answers come only from the uploaded paper, with page citations
- **Out-of-context detection:** unrelated questions (e.g. "Who is the Prime Minister of India?") are refused
- **Follow-up questions:** pronouns like "it" and "they" are resolved using conversation memory
- **Evaluation:** ROUGE and BERTScore for summaries; Precision, Recall and Hit@K for retrieval
- **Fallback modes:** works in extractive mode even without an LLM API key
- **History:** documents, summaries and chats stored in SQLite

## Tech stack
- **Language:** Python
- **PDF extraction:** PyMuPDF
- **Embeddings:** sentence-transformers (all-MiniLM-L6-v2)
- **Vector database:** FAISS
- **LLM:** Google Gemini (default), with OpenAI-compatible and Hugging Face options
- **Database:** SQLite
- **Interface:** Gradio
- **Evaluation:** rouge-score, bert-score

## How it works
Upload PDF -> extract text page by page -> clean -> chunk (with overlap) -> embed -> store in FAISS -> retrieve top matching chunks for a question -> LLM answers using only those chunks.

## How to run
1. Download `Research_Paper_RAG_System.ipynb`
2. Open it in Google Colab or Jupyter Notebook
3. (Optional) Set your own API key as an environment variable, for example `GEMINI_API_KEY`. Never paste keys into the notebook.
4. Run all cells in order
5. Open the Gradio interface, upload a PDF, and try the Summary, Key Information and Ask Document tabs

## About
MCA academic team project developed by a group of 6 students.
