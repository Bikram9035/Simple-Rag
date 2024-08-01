# PDF Question-Answering System
This project implements a question-answering system that can process PDF documents, create embeddings, and use a language model to answer questions based on the document content.

### Features

Load and process PDF documents
Split documents into smaller chunks for better processing
Create embeddings using OpenAI's embedding model
Use FAISS for efficient similarity search
Implement a retrieval-based question-answering system using LangChain and OpenAI's GPT model

### Prerequisites
Before running this project, make sure you have the following:

Python 3.7+
An OpenAI API key

### Installation

Clone this repository:
Copygit clone https://github.com/Bikram9035/Simple-Rag.git
cd pdf-qa-system

Install the required packages:
Copypip install -r requirements.txt

Create a .env file in the project root and add your OpenAI API key:
CopyOPENAI_API_KEY=your_api_key_here


### Usage

Place your PDF file (named bestbook.pdf) in the project root directory.
Run the main script:
Copypython main.py

The script will process the PDF, create embeddings, and set up the question-answering system.
You can then ask questions about the content of the PDF, for example:
pythonCopyresponse = retrieval_chain.invoke({"input": "how to activate all chakras"})
print(response['answer'])


### How It Works

The PDF is loaded and split into smaller chunks.
These chunks are converted into embeddings using OpenAI's embedding model.
The embeddings are stored in a FAISS index for efficient similarity search.
When a question is asked, the system retrieves the most relevant chunks from the FAISS index.
The retrieved chunks and the question are passed to a language model (GPT-3.5-turbo) to generate an answer.

### Customization

You can change the chunk_size and chunk_overlap parameters in the RecursiveCharacterTextSplitter to adjust how the document is split.
The ChatPromptTemplate can be modified to change how the question is presented to the language model.
You can experiment with different LLM models by changing the model parameter in the ChatOpenAI initialization.
