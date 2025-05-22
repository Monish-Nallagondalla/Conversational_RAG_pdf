# Conversational RAG with PDF Uploads and Chat History

This repository contains a Conversational Retrieval-Augmented Generation (RAG) system built with Streamlit, enabling users to upload PDF files, process their content, and ask questions with chat history awareness. The system uses LangChain for document processing and retrieval, Groq's Gemma2-9b-It model for question answering, HuggingFace embeddings for vectorization, and Chroma for vector storage.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [File Structure](#file-structure)
- [Setup Instructions](#setup-instructions)
- [Requirements](#requirements)
- [Usage](#usage)
- [License](#license)

## Overview
The project implements a conversational Q&A system that allows users to upload PDF documents, processes them into a vector store using HuggingFace embeddings (`all-MiniLM-L6-v2`), and answers queries based on the document content. It incorporates chat history to contextualize follow-up questions, using LangChain's history-aware retriever and Groq's Gemma2-9b-It model for concise, accurate responses. The system is deployed via a Streamlit web interface for user-friendly interaction.

## Features
- Streamlit interface for uploading multiple PDF files and querying their content.
- Conversational RAG with chat history support for context-aware question answering.
- Uses HuggingFace's `all-MiniLM-L6-v2` for document embeddings.
- Powered by Groq's Gemma2-9b-It model for fast and accurate responses.
- Chroma vector store for efficient document retrieval.
- Session-based chat history management for multiple users or sessions.
- Displays chat history and responses in the interface.

## File Structure
```
├── .gitignore              # Git ignore file for excluding unnecessary files
├── LICENSE                 # License file (MIT)
├── README.md               # Project documentation
├── app.py                  # Main application with Conversational RAG implementation
├── requirements.txt         # Python dependencies
└── temp.pdf                # Temporary file for processing uploaded PDFs (generated at runtime)
```

## Setup Instructions
1. **Clone the Repository**
   ```bash
   git clone https://github.com/Monish-Nallagondalla/Conversational_RAG_pdf.git
   cd Conversational_RAG_pdf
   ```

2. **Install Dependencies**
   Ensure you have Python 3.8+ installed. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**
   - Create a `.env` file in the project root:
     ```bash
     touch .env
     ```
   - Add the necessary API keys:
     ```plaintext
     GROQ_API_KEY=your_groq_api_key
     HF_TOKEN=your_huggingface_token
     ```
   - Obtain API keys:
     - Groq API: Sign up at [console.groq.com](https://console.groq.com).
     - HuggingFace Token: Generate at [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens).

4. **Run the Application**
   ```bash
   streamlit run app.py
   ```

## Requirements
The dependencies are listed in `requirements.txt`. Key packages include:
```
streamlit
langchain
langchain-groq
langchain-chroma
langchain-huggingface
langchain-community
pypdf
python-dotenv
```

## Usage
1. Launch the Streamlit app using the instructions above.
2. Enter your Groq API key in the provided text input (password-protected field).
3. Specify a session ID (default is `default_session`) to track chat history.
4. Upload one or more PDF files using the file uploader.
5. Enter a question related to the uploaded PDFs in the text input field.
6. View the assistant's response and the chat history, which includes previous interactions.
7. Use the interface to ask follow-up questions, leveraging the chat history for context.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
