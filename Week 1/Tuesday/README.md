# Week 1: Tuesday Session

In today's assignment, we'll be creating a simplified RAQA system using OpenAI, LangChain, FAISS, and Chainlit.

There are 3 main sections to this assignment:

## Build 🏗️

Following the provided notebook - you'll build a simplified RAQA system to ask questions over some reviews of the movie Barbie.

This will take you through three major steps: 

1. Collecting and parsing data
2. Building an Index (VectorStore)
3. Chaining your Index together with an OpenAI LLM model.

### Deliverables

- Completed Notebook
- System Diagram of the RAQA Application

## Ship 🚢

Duplicate the provided [Hugging Face Space](https://huggingface.co/spaces/ai-maker-space/Barbie-RAQA-Application-Chainlit-Demo)

### Deliverables

- A short Loom of the space, and a 1min. walkthrough of the application in full

## Share 🚀

Make a social media post about your final application!

### Deliverables

- Make a post on any social media platform about what you built!

# Bare-bones RAQA implementation

INDEX SYSTEM:
- Load documents
- Chunk documents
- Embed documents
- Store embeddings with their corresponding text forms in a VectorStore

RETRIEVAL SYSTEM:
- Obtain user query.
- Embed user query in the same space as your corpus of documents
- Vector search for relevant documents based on your embedded user query
- Return top_k relevant documents, along with user query as text

AUGMENT SYSTEM:
- Create initial prompt with user query (text form)
- Augment prompt with retrieved context
- Send augmented prompt to LLM
- Receive response
- Based on the tools you mentioned - let's go step by step through which tool and how it aligns with the above, but I'm going to add one extra tool:

1) LLM
2) Vector store
3) Vector store retriever
4) Embedder
5) Prompt
6) Document loader
7) Document chunker
8) User input

INDEX SYSTEM:
- Load documents (Document loader)
- Chunk documents (Document chunker)
- Embed documents (Embedder)
- Store embeddings with their corresponding text forms in a VectorStore (Vector store)

RETRIEVAL SYSTEM:
- Obtain user query (User input)
- Embed user query in the same space as your corpus of documents (Embedder)
- Vector search for relevant documents based on your embedded user query (Vector store retriever)
- Return top_k relevant documents, along with user query as text (Vector store retriever)

AUGMENT SYSTEM:
- Create initial prompt with user query (text form) (Prompt + User input)
- Augment prompt with retrieved context (Prompt + Vector store retriever)
- Send augmented prompt to LLM (LLM)
- Receive response (LLM)
