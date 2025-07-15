Microsoft 2022 Annual Report RAG Pipeline
This project implements a Retrieval-Augmented Generation (RAG) pipeline to extract insights from the Microsoft 2022 Annual Report using Google's Gemini models, LangChain, ChromaDB, and other Python libraries. The pipeline processes a PDF document, generates embeddings, stores them in a vector database, and answers financial queries with robust error handling.
Features

PDF Parsing: Extracts and cleans text from the Microsoft 2022 Annual Report PDF using pypdf.
Text Chunking: Splits text into manageable chunks with LangChain's RecursiveCharacterTextSplitter.
Embedding Generation: Uses Google's Gemini embedding-001 model to create vector embeddings.
Vector Storage and Retrieval: Stores embeddings in ChromaDB and retrieves relevant documents for queries.
Generative Question-Answering: Leverages Gemini's gemini-2.5-flash-preview-05-20 model to answer financial questions based on retrieved documents.
Error Handling: Includes checks for missing files, empty pages, and unavailable utility modules.
Colab Integration: Securely handles API keys via Google Colab's userdata for seamless execution.

Prerequisites

Python 3.8+
Google Colab environment (recommended) or a local Python environment with equivalent dependencies
A Google API key with access to Gemini models (set as a Colab secret named GOOGLE_API_KEY or as an environment variable)
The microsoft_annual_report_2022.pdf file uploaded to the working directory

Installation

Clone this repository:
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name


Install the required dependencies:
pip install gspread pandas pypdf chromadb sentence-transformers numpy scipy scikit-learn google-generativeai


Ensure the microsoft_annual_report_2022.pdf file is in the project directory.

(For Colab) Set your Google API key:

Go to Colab's "Secrets" panel.
Add a secret named GOOGLE_API_KEY with your Google API key.



Usage

Open the main script (main.py or equivalent Jupyter notebook) in Google Colab or your local environment.
Ensure the PDF file is available in the working directory.
Run the script to:
Extract and clean text from the PDF.
Split text into chunks and generate embeddings.
Store embeddings in ChromaDB.
Query the pipeline (e.g., "What was the total revenue?") to retrieve and generate answers.



Example query output:
query = "What was the total revenue?"
# The pipeline retrieves relevant document chunks and generates a response using Gemini.

Project Structure

main.py (or equivalent notebook): Core script containing the RAG pipeline logic.
microsoft_annual_report_2022.pdf: Input PDF file (not included; must be provided by the user).
README.md: This file, providing project overview and instructions.

Dependencies

gspread: For Google Sheets integration (if used).
pandas: For data manipulation.
pypdf: For PDF text extraction.
langchain: For text chunking with RecursiveCharacterTextSplitter.
chromadb: For vector storage and retrieval.
sentence-transformers: For text embeddings (optional fallback).
numpy, scipy, scikit-learn: For numerical and machine learning utilities.
google-generativeai: For Gemini model integration.

Notes

The helper_utils library is not used due to its unavailability on PyPI. A custom word_wrap function is implemented as a fallback.
Ensure the Google API key is correctly configured to avoid authentication errors.
The pipeline is designed for Google Colab but can be adapted for local environments with minor changes (e.g., environment variable setup for the API key).
The Gemini model used for embeddings is models/embedding-001, and for generation, models/gemini-2.5-flash-preview-05-20.

Acknowledgments

DeepLearning.AI: For the Advanced Retrieval for AI course, which provided insights into chunking and vector search strategies.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or contributions, please open an issue or contact [your-username] on GitHub.
#RAG #LangChain #ChromaDB #Gemini #GenerativeAI #AIinFinance #DocumentIntelligence #Python #NLP #LLM #DeepLearningAI #InformationRetrieval #Mentorship
