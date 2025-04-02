# 🤖✨ Meet Your AI Mirror: Get to Know Amir... via Amir

Welcome to **PersonaRAG** — your backstage pass to the mind of **Amir Ghadami**.

This isn’t just another chatbot. This is *your personal AI-powered career oracle*. It’s like giving GPT-4o a tour through your brain — resume, goals, projects, life plans, dreams, PhD ambitions, even your ideal mansion and family plan by 40. 🎯

Ever wanted to ask questions like:
> 🧠 “What’s Amir working on right now?”  
> 📚 “How many papers has he published?”  
> 🔮 “Where does he see himself in 2035?”  
> 🏗️ “Tell me about his most ambitious AI projects.”

Well now you can — *and you’ll get responses as if your future self had already lived through it*.

So ask away. Laugh. Learn. Plot world domination (ethically).  
**PersonaRAG** is here to make your story searchable, sharable, and spectacularly smart.

---

# 🧠💼 PersonaRAG

**PersonaRAG** is an AI-powered chatbot that knows your career inside and out. It uses Retrieval-Augmented Generation (RAG) to interactively answer questions about your resume, publications, projects, and future goals—like having a personal assistant trained on your portfolio.

🦪 The name **PersonaRAG** reflects the fusion of your personal narrative with cutting-edge retrieval-based AI.

---

## ✨ Features

### 📄 Resume + Project Intelligence
- Uploads and processes markdown files containing your resume, research, and projects.
- Organizes by document type: pubs, projs, goals, etc.

### 🔍 Vector Retrieval with Chroma
- Converts your content into high-dimensional vector embeddings for semantic search.
- Uses OpenAI’s Embedding API or HuggingFace alternative.

### 💬 Conversational Q&A with GPT-4o-mini
- A memory-aware chatbot that can field questions like:  
  “What’s your most recent project?”  
  “What are your future goals?”  
  “Tell me about your research.”

### 📊 2D/3D Visualization of Embeddings
- Visualizes how your documents are clustered in vector space using t-SNE.
- Provides intuitive insights into your career landscape.

---

## 📂 Project Structure

```
PersonaRAG/
├── persona_rag.py           # Main RAG logic
├── knowledge-base/          # 🧠 Your personal docs (e.g., resume, pubs, projs, etc)
├── persona_rag.ipynb    # ✅ Full notebook pipeline
├── .env                     # API keys
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/amirgadami/PersonaRAG.git
cd PersonaRAG
```

### 2. Set Up the Environment

```bash
conda env create -f environment.yml
conda activate personarag
```

### 3. Add API Keys

Create a `.env` file:

```bash
OPENAI_API_KEY=your_openai_key
```

### 4. Run the Notebook

```bash
jupyter notebook PersonaRAG_Demo.ipynb
```

---

## 🗛️ Sample Output

Ask your chatbot:
- “Summarize my publications.”
- “What’s BroucheGenA?”
- “What are Amir’s goals for 2025?”

You’ll get tailored responses from your personal knowledge base.

---

## 🤝 Contributing

Open to enhancements! Ideas to explore:
- 🌐 Web-based Gradio UI with file upload  
- 🧠 Fine-tuned personal embedding model  
- 📝 PDF export of conversation history

---

## 📣 Contact

Made with ❤️ by **Amir Ghadami**

- 📧 Email: ah.ghadami75@gmail.com  
- 🔗 LinkedIn: [Amirhossein Ghadami](https://www.linkedin.com/in/amirhosseinghadami/)  
- 🕴️ Twitter (X): [@Amir_ghadamii](https://x.com/Amir_ghadamii)

---

## 🧪 License

This project is licensed under the MIT License. See the LICENSE file for more info.
