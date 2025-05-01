
# MediBot – Medical Chatbot with LangChain & Mistral 7B

MediBot is an AI-powered chatbot that answers medical questions using data from the **Gale Encyclopedia of Medicine**. It leverages **LangChain**, **FAISS**, and the **Mistral 7B-Instruct** model hosted on HuggingFace. The chatbot is built with **Streamlit** for an interactive web UI.

## Features

- Natural language question-answering over medical PDFs
- Uses HuggingFace `mistralai/Mistral-7B-Instruct-v0.3` for high-quality responses
- Retrieves relevant context using FAISS vector store
- Supports `.env` for secure HuggingFace API token management

## Tech Stack

-  LangChain
-  PDF ingestion & embeddings (MiniLM)
-  Mistral 7B LLM via HuggingFace Inference API
-  FAISS vector store
-  Streamlit frontend

##  Folder Structure

```
medical-chatbot
 ┣ vectorstore/           ← FAISS vector DB
 ┣ medibot.py             ← Main Streamlit app
 ┣ .gitignore             ← Ignore secrets & venv
 ┣ .env                   ← Your HuggingFace token (excluded from Git)
 ┗ README.md              ← This file
```

## Setup Instructions

1. **Clone the repo or upload files to GitHub**

   If you are using GitHub, upload the files to a new repository.

2. **Install dependencies:**

   Install all the required dependencies by running:

   ```bash
   pip install -r requirements.txt
   ```

3. **Add your HuggingFace token to a `.env` file:**

   Create a `.env` file in the root of the project and add your HuggingFace token like so:

   ```env
   HF_TOKEN=your_huggingface_token_here
   ```

   You can get your HuggingFace token from [HuggingFace](https://huggingface.co/).

4. **Run the app:**

   Run the Streamlit app with the following command:

   ```bash
   streamlit run medibot.py
   ```

   This will open the app in your web browser, where you can interact with the chatbot.

## Example Prompt

> *"What are the goals of cancer treatment?"*

After entering your query, MediBot will return a factual, sourced response based on the embedded documents.

## Accessing the Model

This chatbot uses the **Mistral-7B-Instruct-v0.3** model from HuggingFace. The `LangChain` library is used to manage the integration of embeddings, vector stores, and the question-answering flow.

## Important Notes

- **Security:** The `.env` file contains your HuggingFace API token, which should never be exposed publicly. Ensure that the `.env` file is **added to `.gitignore`** to avoid uploading sensitive information to your GitHub repository.
  
- **PDFs**: The chatbot is designed to extract and use data from a PDF document (like **Gale Encyclopedia of Medicine**), which you will need to embed into the FAISS vector store for the chatbot to retrieve relevant information.

- **Data Source**: Make sure your PDFs are properly pre-processed and vectorized before being added to the FAISS store.

## Disclaimer

MediBot is intended for **educational and informational** purposes only. It is not a substitute for professional medical advice. Always consult with a healthcare professional for any medical concerns.
