# Multimodal RAG Pipeline

An extension of single-document RAG into multimodal retrieval — answering questions from a product manual (AquaPure X1) that combines text, tables, and embedded diagrams/figures.

## What it does
- Parses a multimodal PDF manual, extracting text, tables, and figures (front panel, filter layout, water flow diagrams)
- Generates embeddings for both text and image content
- Stores multimodal embeddings in ChromaDB for combined retrieval
- Answers questions that require reasoning across text and visual content (e.g., diagram-based queries)
- Evaluated against a predefined question set spanning text-only and visual-grounded questions

## Tech Stack
Python, RAG, ChromaDB, LangChain, PDF/image extraction tools, OpenAI API (GPT-4 Vision), Google Gemini API 

## Project Structure

```
├── figures/ #-----------> Extracted diagram images
├── AquaPure_X1_Multimodal_Manual.pdf
├── Evaluation_Questions.csv #-------> Test queries
├── Multi_modal_RAG.ipynb #----------> Main multimodal RAG pipeline (OpenAI)
├── Multi_RAG_Gemini_test.ipynb #----> Gemini variant
└── Requirements.txt
```

## Setup
1. Clone the repo and install dependencies:
```bash
   pip install -r requirements.txt
```
2. Create a `.env` file in the root directory:

GOOGLE_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here

3. Run `Multi_modal_RAG.ipynb` (OpenAI) or `Multi_RAG_Gemini_test.ipynb` (Gemini) end-to-end in Jupyter.

## Notes
Builds directly on [P1_Single_RAG](#), extending single-document text retrieval into multimodal (text + image) retrieval and reasoning — a step toward the Agentic AI work in [Interviewer_Agent_Autogen](#).