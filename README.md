# 📦 Inventory Spotter AI

**Inventory Spotter AI** is an end-to-end, AI-powered warehouse inventory assistant. It processes a grocery warehouse dataset, detects items expiring soon, generates embeddings for semantic search, enables intelligent Q&A via a chatbot, dispatches expiry alerts via voice call, and provides a beautiful Streamlit dashboard for interactive queries. 

---

## 🚀 Features

- **Data Pipeline**: Cleans and processes inventory CSVs, flags items expiring soon, and outputs a structured JSONL file.
- **Embeddings & Semantic Search**: Converts inventory records into vector embeddings using HuggingFace and FAISS for fast, context-aware retrieval.
- **Conversational QA**: Uses LangChain + Ollama (phi3) to answer natural language queries about your stock, locations, or expiry details.
- **Voice Alerts**: Aggregates expiry information and sends automated voice calls via OmniDimension for proactive inventory management.
- **Streamlit Dashboard**: Sleek web UI with example queries, styled components, and instant answers with source traceability.
- **Pathway Integration**: Utilizes [Pathway](https://pathway.com) for high-performance, scalable, and reactive data pipelines to process large inventory datasets efficiently.

---

## 🗂️ Project Structure

```
.
├── data/
│   ├── uploads/Grocery_Inventory_and_Sales_Dataset.csv
│   └── processed/output.jsonl
├── vectorstore/
│   └── faiss_index/
├── main_pipeline.py
├── embed_inventory.py
├── voice_alerts.py
├── app.py
└── README.md
```

---

## ⚙️ Setup & Installation

### 1. **Clone the Repository**

```bash
git clone https://github.com/your-username/inventory-spotter-ai.git
cd inventory-spotter-ai
```

### 2. **Install Dependencies**

```bash
pip install pathway pandas langchain streamlit faiss-cpu huggingface-hub
pip install langchain_community ollama omnidimension
```

> **Note**: For Ollama LLM, ensure you have the [Ollama server](https://ollama.com) running locally and `phi3` model downloaded.

### 3. **Prepare Data**

- Place your warehouse CSV at `data/uploads/Grocery_Inventory_and_Sales_Dataset.csv`.

### 4. **Run Data Pipeline**

```bash
python main_pipeline.py
```
- Processes the CSV using **Pathway**, flags expiring items, saves clean JSONL to `data/processed/output.jsonl`.

### 5. **Build Embeddings Vectorstore**

```bash
python embed_inventory.py
```
- Creates FAISS index for semantic search at `vectorstore/faiss_index`.

### 6. **Test Voice Alerts**

Set your OmniDimension API key, agent ID, and phone number in `voice_alerts.py`. Then:

```bash
python voice_alerts.py
```
- Sends a voice call alert with upcoming expiry info.

### 7. **Launch the Streamlit Dashboard**

```bash
streamlit run app.py
```
- Opens the Inventory Spotter AI dashboard in your browser.

---

## 💡 Example Queries

- *What is the current stock of Digestive Biscuit?*
- *Which items are located in Aisle F?*
- *What’s expiring in July?*
- *Where is Basmati Rice stored?*

---

## 🧠 How It Works

1. **ETL Pipeline**: Cleans, deduplicates, and augments the raw inventory data using **Pathway** for robust, reactive stream processing.
2. **Embeddings Generation**: Each inventory record is summarized and embedded for semantic similarity search.
3. **Retrieval QA Chain**: When you ask a question, the system finds the most relevant records and uses Ollama LLM to answer, citing the source.
4. **Expiry Alerts**: Aggregates items expiring in the next two months and dispatches a voice call alert via OmniDimension.
5. **Streamlit UI**: Interactive, fast, and beautiful — ask free-text questions and see both answers and source snippets.

---

## 🔐 Security & Privacy

- All data is processed and stored locally.
- Voice call features require your OmniDimension credentials; **never share your secrets** publicly.
- Ollama LLM runs locally, so your queries never leave your machine.

---

## 🤝 Credits

- [Pathway](https://pathway.com) for efficient streaming data processing
- [LangChain](https://langchain.com) for LLM orchestration
- [Ollama](https://ollama.com) for local, privacy-preserving LLM inference
- [FAISS](https://github.com/facebookresearch/faiss) for fast vector search
- [OmniDimension](https://omnidimension.com) for AI-powered voice calling

---

## 🛠️ Troubleshooting

- **Ollama not running?**  
  Run `ollama serve` and pull the `phi3` model:  
  `ollama pull phi3`
- **CSV file not found?**  
  Ensure your CSV is at `data/uploads/Grocery_Inventory_and_Sales_Dataset.csv`.
- **Voice call failed?**  
  Check your API key, agent ID, and phone number. See logs for details.

---

## 📜 License

MIT License. See `LICENSE` file for details.

---

## ✨ Demo Screenshots



---

**Inventory Spotter AI — The smarter way to manage your warehouse.** 🚛
