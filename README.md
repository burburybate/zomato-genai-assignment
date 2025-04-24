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
git clone https://github.com/burburybate/zomato-genai-assignment
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

### **Challenges Faced and Solutions**

1.⁠ ⁠*Schema Evolution & Idempotency*:
   - *Challenge*: Re-running the scraper risked duplicating tables or stale data.
   - *Solution*: Added ⁠ DROP TABLE IF EXISTS ⁠ and ⁠ CREATE TABLE IF NOT EXISTS ⁠ guards, and parameterized table names by restaurant ID.
2.⁠ ⁠*Local Development vs. Production*:
   - *Challenge*: Environment differences between Colab, local machines, and deployment servers.
   - *Solution*: Abstracted file paths using ⁠ os.path ⁠ to resolve base directories, enabling consistent behavior across environments.
3.⁠ ⁠*LLM Grounding & Prompt Length*:
   - *Challenge*: Including too much context (all restaurants and menus) could exceed token limits.
   - *Solution*: Limited to top-k retrieved contexts and concatenated only restaurant metadata once, keeping prompts concise.
4.⁠ ⁠*Embedding Scalability*:
   - *Challenge*: Encoding thousands of menu items in one shot risked memory pressure.
   - *Solution*: Used batch encoding and checkpointed intermediate results, then freed unused variables promptly.
5.⁠ ⁠*Embedding Scalability*:
   - *Challenge*: Some restaurant websites lacked essential info like location, contact details, or hours.
   - *Solution*:  For these cases only, default values were manually hardcoded into the database.





### 🧪 **Future Improvements**
- Integrate real-time web scraping
- Add feedback loop for improving answer quality
- Explore multilingual support

### 😀 **Colab**
- Upload the attached our-menus.txt file to your google drive at my drive. ("/content/drive/My Drive/our-menus.txt")




