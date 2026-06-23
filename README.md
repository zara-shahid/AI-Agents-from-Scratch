# AI Agents from Scratch 🤖

A structured learning journey to understand and build AI agents step-by-step, from LLM fundamentals to tool calling capabilities. This repository contains interactive Jupyter notebooks and projects[...]

## 📚 Repository Structure

This project is organized into progressive learning steps, each building on the previous one:

### **Step 1: LLM Fundamentals**
Learn how Large Language Models actually work under the hood before diving into agent building.

- **Topics Covered:**
  - What LLMs are (next-token predictors)
  - Tokenization and why it matters
  - Context windows and limitations
  - Pre-training vs fine-tuning
  - RLHF (Reinforcement Learning from Human Feedback)
  - Core prompting techniques (zero-shot, few-shot, chain of thought)

- **Resources:**
  - *Intro to Large Language Models* - Andrej Karpathy ([YouTube](https://www.youtube.com/watch?v=zjkBMFhNj_g))
  - *ChatGPT Prompt Engineering for Developers* - DeepLearning.AI ([Course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/))

- **Key Takeaway:** An LLM is not a search engine—it's a reasoning engine. Agents give this reasoning engine the ability to take actions.

---

### **Step 2: LLM API Fundamentals**
Learn how to interact with LLM APIs programmatically and build your first AI applications.

**Notebooks:**
- `LLM_APIs_Learning.ipynb` - Learn how to call LLM APIs, handle responses, and manage costs
- `Meeting_Notes_Extractor_Project.ipynb` - Build a practical project that extracts key information from meeting notes

**Setup:**
1. Copy `.env.example` to `.env` and add your API keys
2. Install dependencies: `pip install -r requirements.txt`

---

### **Step 3: Tool Calling**
Master the art of making LLMs call external tools and functions—the foundation of AI agents.

**Notebooks:**
- `tool_calling.ipynb` - Learn function calling, how models decide when to use tools, and building function schemas

**Setup:**
1. Copy `.env.example` to `.env` and add your API keys
2. Install dependencies: `pip install -r requirements.txt`

---

### **Step 4: Embeddings**
Understand embeddings and how vector representations enable semantic search, similarity, and external memory for agents.

**Notebooks:**
- `embeddings_intro.ipynb` - What embeddings are and how they're computed
- `vector_store_demo.ipynb` - Build a small vector store and query it with cosine similarity

**Topics Covered:**
- What embeddings represent and common embedding models
- Building and maintaining a vector store (FAISS, Annoy, or simple in-memory vectors)
- Similarity search and nearest-neighbor retrieval
- Use cases: semantic search, clustering, and retrieval for agents

**Setup:**
1. Copy `.env.example` to `.env` and add your API keys
2. Install dependencies: `pip install -r requirements.txt`

---

### **Step 5: RAG (Retrieval-Augmented Generation)**
Combine retrieval with generation to build agents that answer questions using external knowledge sources.

**Notebooks:**
- `rag_workflow.ipynb` - Implement a simple RAG pipeline: chunking, embedding, retrieval, and generation
- `rag_agent_project.ipynb` - Build an agent that uses RAG to answer questions from a document collection

**Topics Covered:**
- Document chunking and embedding
- Retrieving relevant context and conditioning the LLM
- Pipelines: retrieval -> LLM -> re-ranking / synthesis
- Evaluating RAG systems and trade-offs (latency, freshness, hallucinations)

**Setup:**
1. Copy `.env.example` to `.env` and add your API keys
2. Install dependencies: `pip install -r requirements.txt`

---

## 🎯 What You'll Learn

By working through this repository, you'll understand:

1. ✅ **How LLMs work** - Beyond the hype, the actual mechanics
2. ✅ **How to use LLM APIs** - Practical integration with real models
3. ✅ **How agents make decisions** - Tool calling, function schemas, and action loops
4. ✅ **How to use embeddings** - Semantic representations and vector stores
5. ✅ **How to build RAG-driven agents** - Retrieval + generation pipelines for grounded responses

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or JupyterLab
- API keys for LLM providers (e.g., OpenAI)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/zara-shahid/AI-Agents-from-Scratch.git
   cd AI-Agents-from-Scratch
   ```

2. **For each step, follow the local setup:**
   ```bash
   cd Step_2_LLM_API_Fundamentals  # or Step_3_Tool_Calling or Step_4_Embeddings or Step_5_RAG
   pip install -r requirements.txt
   cp .env.example .env
   # Add your API keys to .env
   ```

3. **Launch Jupyter:**
   ```bash
   jupyter notebook
   ```

4. **Start with Step 1** and progress through each step in order.

---

## 💡 Learning Path

**Complete Beginner?** Start here:
1. Read Step 1 README to understand LLM fundamentals
2. Watch Andrej Karpathy's "Intro to LLMs" video
3. Work through Step 2 notebooks interactively
4. Build the Meeting Notes Extractor project
5. Dive into Step 3 to master tool calling
6. Learn embeddings in Step 4 and build a vector store
7. Apply Retrieval-Augmented Generation in Step 5 to ground agents in external data

**Already familiar with LLMs?** Start with:
1. Step 2 API fundamentals
2. Step 3 tool calling
3. Use these concepts to build your own agents

---

## 🛠️ Technologies & Tools

- **Python 3.8+**
- **Jupyter Notebooks** - Interactive learning environment
- **LLM APIs** - OpenAI, Anthropic, or other providers
- **Environment variables** - Secure API key management with `.env` files

---

## 📖 Key Concepts

### Context Window
Everything the model knows is inside its context window. The model has no memory outside of what is currently in the context—this is why agents need external memory tools.

### Tokenization
LLMs read tokens (chunks of characters), not words. This is why they struggle with character-level tasks and why prompt design matters.

### Function Calling
Models can call external functions to gather information, perform calculations, or interact with systems—this is the foundation of AI agents.

### Agent Loop
Agents work in cycles:
1. **Observe** - Read the current state/conversation
2. **Think** - Decide what action to take
3. **Act** - Call a tool or function
4. **Update** - Add results back to context
5. **Repeat** - Continue until goal is reached

---

## 🤝 Contributing

This is a learning-focused repository. If you find improvements, clarifications, or additional projects that fit the learning path, feel free to open an issue or pull request.

---

## 📝 License

This repository is open source and available under the MIT License.

---

## 🙏 Acknowledgments

- **Andrej Karpathy** - For the excellent "Intro to LLMs" video
- **DeepLearning.AI** - For the ChatGPT Prompt Engineering course
- The open-source ML community - For making these tools accessible

---

## 📞 Questions or Feedback?

Have questions about any of the concepts? Found something unclear? 
- Open an issue in the repository
- Check the individual step READMEs for more context
- Review the notebook comments for deeper explanations

---

**Happy learning! 🚀 Let's build AI agents from scratch together.**
