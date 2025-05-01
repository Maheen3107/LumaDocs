# LumaDocs

<div align="center">
  <img src="/api/placeholder/300/100" alt="LumaDocs Logo" />
  <p>Interactive PDF Analysis and Q&A Platform with AI</p>
</div>

## 📋 Overview

LumaDocs is an intelligent document analysis platform that leverages Google's Gemini AI to enable interactive question-answering with your PDF documents. The application extracts, processes, and vectorizes PDF content, allowing users to ask natural language questions and receive detailed answers based on the document content, complemented by relevant web search results and images.

## ✨ Key Features

- **PDF Processing**: Upload and process multiple PDF documents for analysis
- **AI-Powered Q&A**: Ask natural language questions about your documents and get intelligent answers
- **Source Citations**: Answers include page references and document sources
- **Web Integration**: Automatically fetch relevant web search results related to your questions
- **Image Search**: Display relevant images to enhance understanding of topics
- **Real-time Responses**: Stream responses with a natural typing effect
- **Formatted Output**: Clean HTML formatting for better readability of results
- **Vector Storage**: Efficient document retrieval using FAISS vector database

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Flask
- Google API keys (for Gemini AI and Google Search)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Maheen3107/LumaDocs.git
   cd LumaDocs
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables (create a `.env` file):
   ```
   GOOGLE_API_KEY=your_gemini_api_key
   GOOGLE_SEARCH_API_KEY=your_google_search_api_key
   GOOGLE_SEARCH_CX=your_google_custom_search_id
   ```

5. Start the application:
   ```bash
   python app.py
   ```

6. Open your browser and go to `http://127.0.0.1:8000`

## 📚 How It Works

1. **Document Upload**: Upload your PDF documents via the web interface
2. **Text Extraction**: The system extracts text content from each page of the PDFs
3. **Chunking**: Text is split into manageable chunks with metadata (source and page number)
4. **Vectorization**: Text chunks are converted to vector embeddings using Google's embedding model
5. **Storage**: Vectors are stored in a FAISS index for efficient similarity search
6. **Q&A Process**: 
   - When a question is asked, the system finds the most relevant text chunks
   - The Gemini model generates a comprehensive answer based on the relevant chunks
   - Web search and image results enhance the answer with additional context
   - Results are streamed to the user with proper formatting and citations

## 🧩 System Components

- **Flask**: Web framework for the application
- **Socket.IO**: Real-time communication for streaming responses
- **Langchain**: Framework for working with LLMs
- **Google Gemini AI**: Powers the core Q&A functionality
- **FAISS**: Vector database for efficient similarity search
- **PyPDF2**: PDF parsing library
- **Google Custom Search API**: Provides web and image search capabilities

## 🔧 Technical Details

### API Routes

- **`/`**: Main application interface
- **`/upload`**: Endpoint for PDF document uploads (POST)
- **`/status`**: Check if vector index is available (GET)

### Socket.IO Events

- **`ask_question`**: Event to send questions to the backend
- **`response`**: Event to receive streaming responses from the backend

### Answer Formatting

Responses are formatted with structured HTML for better readability:
- Main headings using `<h2>` tags
- Subheadings using `<h3>` tags
- Important text in bold using `<b>` tags
- Organized lists using `<ul>` and `<li>` tags
- Highlighted phrases using `<mark>` tags
- Special notes using custom styled divs

## 📝 Requirements

```
flask
flask-socketio
PyPDF2
langchain
langchain-google-genai
google-generativeai
faiss-cpu
requests
python-dotenv
```

## 🔄 Future Enhancements

- Document management interface for organizing multiple PDFs
- Customizable prompt templates for different types of analysis
- PDF annotation and highlighting capabilities
- Export functionality for Q&A sessions
- Authentication system for secure document storage
- Chat history persistence

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Contact

Maheen - [@Maheen3107](https://github.com/Maheen3107)

Project Link: [https://github.com/Maheen3107/LumaDocs](https://github.com/Maheen3107/LumaDocs)
