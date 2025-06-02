# PDF-based Q\&A with LangChain, AstraDB, and OpenAI

This project demonstrates how to create a Question-Answering (QA) system using **LangChain**, **OpenAI**, and **AstraDB** (by **DataStax**). The system reads a PDF (e.g., a budget speech), splits the text into manageable chunks, stores them as vector embeddings in AstraDB, and allows semantic search and LLM-based querying.

## Features

* Extract text from PDFs using `PyPDF2`
* Chunk and embed the text with `LangChain` tools
* Store vector embeddings in **AstraDB** using the `Cassandra` vector store interface
* Query stored content using **OpenAI GPT** via **LangChain**
* Scalable and cloud-native vector storage using **DataStax AstraDB**

## Setup Instructions

**Clone the Repository**

```bash
git clone https://github.com/your-username/langchain-astradb-pdf-qa.git
cd langchain-astradb-pdf-qa
```

**Install Dependencies**

```cmd
pip install -r requirements.txt
```

**Add Environment Variables**

Create a `.env` file and add your OpenAI API key:

```
OPENAI_API_KEY=your_openai_key_here
```

**Update AstraDB Credentials**

In your Python script, set:

```python
ASTRA_DB_APPLICATION_TOKEN = "your_astra_application_token"
ASTRA_DB_ID = "your_astra_db_id"
```

## How It Works

1. PDF is read and its text extracted using `PyPDF2`.
2. The text is split into overlapping chunks to maintain context using `CharacterTextSplitter`.
3. Chunks are embedded with OpenAI's embedding model.
4. The vector data is stored in **AstraDB**, a serverless, distributed NoSQL database.
5. You can ask natural language questions, which are answered by querying AstraDB and running results through OpenAI’s LLM.

## Why AstraDB?

**AstraDB**, by **DataStax**, is a modern database-as-a-service built on Apache Cassandra®, tailored for cloud-native applications. It's ideal for vector search and large-scale AI workloads because:

* It’s serverless, scalable, and highly available
* Provides native vector search capabilities
* Integrates seamlessly with LangChain using `cassio`
* Developer-friendly with generous free tiers

[Start with AstraDB for free](https://www.datastax.com/astra)
