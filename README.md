# Enterprise Financial Document Intelligence & RAG Agent

An end-to-end Retrieval-Augmented Generation (RAG) system engineered in Python to parse unstructured enterprise 10-K financial filings, vectorize financial statements into dense embeddings, and execute deterministic similarity search with source verification.

---

## 💼 Enterprise Problem & Architecture
Analyzing multi-hundred-page corporate earnings reports and SEC filings manually is slow and prone to missed disclosures. Off-the-shelf generative models frequently hallucinate quantitative figures. This pipeline enforces deterministic document chunking, localized vector storage, and distance-scored semantic retrieval to ensure all extracted figures correlate directly to verifiable source disclosures.
Unstructured 10-K Disclosure
│
▼
[Recursive Text Chunking (200 chars / 40 overlap)]
│
▼
[Sentence-Transformers Embeddings (MiniLM-L6-v2)]
│
▼
[ChromaDB Local Vector Database]
│
├──► Analytical Query ("CapEx Allocations")
│
▼
[Cosine Similarity Search + Source Evidence Output]


---

## 🔑 Key Engineering Deliverables
- **Semantic Text Segmentation:** Deployed recursive text splitting preserving quantitative context, line breaks, and accounting metrics.
- **Transformer Vectorization:** Embedded raw financial text using Hugging Face's `all-MiniLM-L6-v2` dense vector representations.
- **Vector Database Indexing:** Implemented an in-memory ChromaDB vector store collection for high-throughput semantic querying.
- **Hallucination Prevention:** Designed retrieval pipelines scoring relevance distances to extract verifiable financial citations.

---

## 🛠️ Tech Stack & Tooling
- **Language:** Python
- **Frameworks:** LangChain, LangChain-Text-Splitters, LangChain-Community
- **Vector Store:** ChromaDB
- **Embedding Models:** Hugging Face Sentence-Transformers (`all-MiniLM-L6-v2`)

    
