# Q-A-using-RAPTOR-and-Milvus-Openai
### Project Overview

This project involves creating a system to extract, process, and analyze text from PDF documents using advanced techniques in Natural Language Processing (NLP) and machine learning. The system is designed to:

1. **Extract Content**: Extract text from PDFs.
2. **Chunk Data**: Break the text into manageable chunks.
3. **Index with RAPTOR**: Apply the RAPTOR method to index the data for efficient retrieval.
4. **Retrieve Documents**: Use hybrid retrieval techniques to find relevant documents based on queries.
5. **Re-Rank Results**: Re-rank the retrieved documents based on relevance.
6. **Answer Questions**: Use a language model to answer questions based on the extracted content.
7.  **Milvus Vector Database Creation**: creating the vector databse using milvus storing the in vector format .

### Detailed Breakdown

#### 1. Content Extraction

**Objective**: Extract text from one or more PDF documents.

- **Tools Used**: PyMuPDF (fitz), PDFMiner, or PyPDF2.
- **Process**: Open the PDF, iterate through its pages, and collect text.


**Example**: Extract text from a PDF file and print the content.

#### 2. Data Chunking

**Objective**: Break the extracted text into smaller, meaningful chunks and embed them into vector representations.

- **Tools Used**: NLTK for text tokenization and Sentence-BERT for embeddings.
- **Process**: Tokenize the text into sentences, group sentences into chunks, and convert each chunk into a vector using Sentence-BERT.

**Example**: Chunk a large text into smaller pieces and create embeddings for each chunk.

#### 3. RAPTOR Indexing

**Objective**: Index the text chunks using the RAPTOR method, which involves clustering and summarization.

- **Tools Used**: scikit-learn for Gaussian Mixture Models (GMMs) and clustering.
- **Process**: 
  - **Clustering**: Apply GMM to cluster text embeddings.
  - **Summarization**: Summarize each cluster to create concise representations.
  - **Re-Embedding**: Create a hierarchical index by re-embedding summarized clusters.

**Example**: Cluster text chunks and summarize clusters for efficient indexing.

#### 4. Retrieval Techniques

**Objective**: Retrieve relevant documents based on user queries using hybrid retrieval methods.

- **Tools Used**: BM25 for traditional retrieval and Sentence-BERT for semantic retrieval.
- **Process**: 
  - **BM25**: Rank documents based on term frequency and inverse document frequency.
  - **Embedding-Based Retrieval**: Use embeddings to find semantically similar documents.

**Example**: Retrieve and rank documents based on a given query.

#### 5. Re-Ranking

**Objective**: Improve retrieval results by re-ranking based on query-document similarity.

- **Tools Used**: Sentence-BERT for computing similarities.
- **Process**: Compute similarity scores between query and document embeddings, then re-rank the documents based on these scores.
- **Script**: `re_ranking/re_ranking.py`

**Example**: Re-rank the initial retrieval results to improve relevance.

### Setup Instructions

1. **Install Dependencies**:
   pip install -r requirements.txt

2. **Create the Milvus Vector Database:**:
Install Milvus: Follow the Milvus installation guide to set up Milvus. You can use Docker for a quick setup.
  

### Selected Textbooks

- **Textbook 1**: RAPTOR: Recursive Abstractive Processing for Tree-Organized Retrieval Paper
- **Textbook 2**:MILVUS Documentation: https://milvus.io/docs/
- **Textbook 3**:- Natural Language Processing with Python" (by Steven Bird, Ewan Klein, and Edward Loper)

