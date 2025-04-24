# Zomato Genai Assignment

# 🍽️ Nugget: AI-powered Restaurant Menu Assistant
Find your perfect dish, across restaurants with natural language search.
NuggetRAG combines local restaurant menu data with semantic search and large language models to answer user queries about dishes, prices, veg/non-veg options, and restaurant availability—all via a sleek Streamlit UI.

![image](https://github.com/user-attachments/assets/83534246-4386-4ce7-8274-8110dcc924fa)

- Natural language querying over restaurant menus
- FAISS-powered semantic retrieval
- Streamlit-based conversational UI
- Integration with Mistral API for accurate answers

# 📦 Installation

Clone the repo and install dependencies:

```bash
git clone https://github.com/yourusername/nuggetrag.git
cd nugget
pip install sentence-transformers faiss-cpu transformers torch streamlit
```


## 🔑 **Environment Variables**
 🔐 Environment Setup

You’ll need to set your Mistral API key as an environment variable:

link to API: https://console.mistral.ai/api-keys

**macOS/Linux:**
```bash
export MISTRAL_API_KEY=your_api_key_here
```
**Windows (PowerShell):**
```bash
$env:MISTRAL_API_KEY="your_api_key_here"
```

### ▶️ **Usage**

To start the app:
```bash
streamlit run nuggetrag.py
```
### 🧠 **How It Works**
High-level overview of your architecture.

- ⁠Scrapes and stores restaurant data into SQLite
- ⁠Uses SentenceTransformer to embed menu item text
- ⁠Builds a FAISS index for fast retrieval
- Retrieves relevant items based on user query
- Mistral API generates natural responses using retrieved context

### 🧩 **Tech Stack**
- Python 3
- Streamlit
- FAISS
- SentenceTransformers
- HuggingFace Transformers
- Mistral API
- SQLite

### 🧪 **Future Improvements**
- Integrate real-time web scraping
- Add feedback loop for improving answer quality
- Explore multilingual support

### 😀 **Colab**
- Upload the attached our-menus.txt file to your google drive at my drive. ("/content/drive/My Drive/our-menus.txt")




