# EPCIS-RAG

Retrieval-Augmented Generation (RAG) on **synthetic EPCIS** data using **vLLM**.  
This project builds a supply chain assistant that can answer natural language questions about traceability events (shipments, receipts, lead times, etc.) while always citing the underlying evidence.

---

## ✨ Goal

- Generate a synthetic dataset of EPCIS events (ObjectEvent, AggregationEvent).
- Index events with embeddings for efficient retrieval (Chroma/FAISS).
- Serve RAG answers with vLLM, including citations to event/shipment IDs.
- Evaluate quality (EM/F1), retrieval (Recall@k), and performance (latency p50/p95).

---

## 🚀 Quickstart

```bash
# 1. Clone repo
git clone https://github.com/<your-username>/epcis-rag.git
cd epcis-rag

# 2. Install dependencies
make install   # or pip install -r requirements.txt

# 3. Generate synthetic dataset
python src/generate_epcis.py

# 4. Build index
python src/build_index.py

# 5. Run a sample query
python src/retrieve.py --query "Which cases were received yesterday at SGLN X?"
