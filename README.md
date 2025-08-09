📄 PDF to Answer – RAG Chatbot

📌 Overview
PDF to Answer is an intelligent chatbot application built using **LangChain** and **Google Generative AI**, designed to read uploaded PDF files and answer user queries based on their content.  
It implements a **full RAG (Retrieval-Augmented Generation) pipeline** — breaking documents into chunks, embedding them into a vector store, retrieving relevant chunks, and generating accurate answers using an LLM.

✨ Features
- 📂 **Upload multiple PDF files** at once.
- 🔍 **Ask natural language questions** about the uploaded content.
- ⚡ **Real-time streaming responses** from the AI model.
- 🔒 Data is stored locally in a **Chroma vector store**.
- 🔁 **Retry mechanism** for clearing and recreating embeddings database.

🛠️ Tech Stack
- **Frontend & UI:** [Streamlit](https://streamlit.io/)
- **PDF Parsing:** [PyPDF2](https://pypi.org/project/PyPDF2/)
- **LLM & Embeddings:** Google Generative AI (`gemini-pro`), Ollama, Replicate
- **Vector Database:** [Chroma](https://www.trychroma.com/)
- **LangChain Components:**  
  - `RecursiveCharacterTextSplitter` for chunking  
  - `GoogleGenerativeAIEmbeddings` for embeddings  
  - `ChatPromptTemplate` for structured prompting  
  - `StrOutputParser` for clean model output
- **Environment Management:** `dotenv` for API keys

## 🚀 How It Works
1. **PDF Upload** → User uploads one or more PDFs.
2. **Text Extraction** → `PyPDF2` extracts raw text from all pages.
3. **Chunking** → Text is split into smaller overlapping chunks using `RecursiveCharacterTextSplitter`.
4. **Embedding Creation** → Chunks are converted to vector embeddings using `GoogleGenerativeAIEmbeddings`.
5. **Storage** → Embeddings are stored locally in a persistent **Chroma** vector store.
6. **Query Processing** → User enters a question; the retriever fetches top-matching chunks.
7. **Answer Generation** → A Large Language Model (`gemini-pro`) generates an accurate and context-aware answer.
