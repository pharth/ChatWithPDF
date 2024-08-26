# ChatWithPDF

This is a Flask web application that provides AI-powered document search and retrieval functionality. It leverages the LangChain framework to process natural language queries and search through PDF documents for relevant information.

## Features

- Process natural language queries with a pre-trained language model.
- Upload and index PDF documents for efficient search and retrieval.
- Retrieve relevant document sections based on query similarity.

## Installation

### Prerequisites

- Python 3.7 or higher

### Setting Up the Environment

1. **Clone the repository:**

   ```sh
   git clone https://github.com/pharth/ChatWithPDF
   cd ChatWithPDF
   ```
2.**Create a virtual environment:**

  ```sh
   python -m venv venv
```
3.**Activate the virtual environment:**
On Windows:

```sh
venv\Scripts\activate
```
On macOS and Linux:

```sh
source venv/bin/activate
```
4.**Install the required packages from requirements.txt:**

```sh
pip install -r requirements.txt
```

## Usage
1.**Run the Flask application:**

```sh
python app.py
```
2.**Endpoints:**

### POST /ai
  
  Processes a natural language query using the language model.

**Request:**

```json
{
  "query": "Your question here"
}
```
**Response:**

```json
{
  "answer": "Response from the language model"
}
```
### POST /ask_pdf

  Queries the indexed PDF documents.

**Request:**

```json
{
  "query": "Your question related to the documents"
}
```

**Response:**

```json
{
  "answer": "Relevant answer from the documents",
  "sources": [
    {
      "source": "source file name",
      "page_content": "relevant page content"
    }
  ]
}
```

### POST /pdf

Uploads and indexes a PDF document.

**Request:**

Form-data with the key "file" and the PDF file as value.

**Response:**

```json
{
  "status": "Successfully Uploaded",
  "filename": "uploaded_file_name.pdf",
  "doc_len": 10,
  "chunks": 20
}
```
