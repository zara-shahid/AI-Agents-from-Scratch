# AI Agents from Scratch 🤖

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)
![Groq](https://img.shields.io/badge/LLM-Groq%20%2B%20LLaMA%203-F55036?style=flat)
![Jupyter](https://img.shields.io/badge/Notebooks-Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

A structured, hands-on learning journey to understand and build AI agents step-by-step — from LLM fundamentals to tool calling, embeddings, and full RAG pipelines. Each step builds on the previous one, documented through interactive Jupyter notebooks and real mini-projects.

---

## 📚 Repository Structure

### ✅ Step 1: LLM Fundamentals
*Status: Complete*

Understand how Large Language Models actually work before building on top of them.

**Topics Covered:**
- What LLMs are — next-token predictors trained on internet-scale text
- Tokenization and why it affects prompt design
- Context windows and their limitations
- Pre-training vs. fine-tuning
- RLHF (Reinforcement Learning from Human Feedback)
- Core prompting techniques: zero-shot, few-shot, chain-of-thought, iterative refinement
- LLM capabilities and limitations: hallucination, context limits, lack of true reasoning

**Resources:**
- *Intro to Large Language Models* — Andrej Karpathy ([YouTube](https://www.youtube.com/watch?v=zjkBMFhNj_g))
- *ChatGPT Prompt Engineering for Developers* — DeepLearning.AI ([Course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/))

> **Key Takeaway:** An LLM is a compressed, lossy representation of internet knowledge — not a search engine but a reasoning engine. Agents give this reasoning engine the ability to take actions.

---

### ✅ Step 2: LLM API Fundamentals
*Status: Complete*

Learn to interact with LLM APIs programmatically and build a first real application.

**Notebooks:**
- `LLM_APIs_Learning.ipynb` — API auth and env setup, `chat.completions.create()`, message roles (system/user/assistant), multi-turn conversations, temperature and max_tokens, structured JSON outputs, error handling, porting code between Groq and OpenAI
- `Meeting_Notes_Extractor_Project.ipynb` — Mini-project: converts raw meeting notes into structured JSON (dates, names, action items) using multi-turn correction loops

**Setup:**
```bash
cd Step_2_LLM_API_Fundamentals
pip install -r requirements.txt
cp .env.example .env
# Add your Groq API key to .env
```

---

### ✅ Step 3: Tool Calling / Function Calling
*Status: Complete*

Master function/tool calling — the core mechanism that turns an LLM into an agent.

**Notebooks:**
- `tool_calling.ipynb` — The complete tool-calling loop, JSON schema definitions, multi-tool agents

**Topics Covered:**
- What tools are and why LLMs need them
- Defining tools via JSON schema (name, description, parameters)
- `tool_choice` options: auto / required / none
- The 5-step tool-calling loop: send → model requests tool → execute → return result → final answer
- Returning results via `role: 'tool'`
- Multi-step calls (same tool twice) and multi-tool setup (model picks the right tool)
- System prompts to constrain model to provided tools only

**Projects Built:**
- **Calculator tool** — exact arithmetic via Python (no hallucinated math)
- **Weather tool** — live data from [wttr.in](https://wttr.in)
- **Combined multi-tool agent** — model selects between both tools dynamically

**Model:** `llama-3.3-70b-versatile` via Groq

**Setup:**
```bash
cd Step_3_Tool_Calling
pip install -r requirements.txt
cp .env.example .env
# Add your Groq API key to .env
```

---

### ✅ Step 4: Embeddings
*Status: Complete*

Understand how text is converted into vectors and how similarity search powers agent memory and retrieval.

**Notebooks:**
- `step4_embeddings.ipynb` — TF-IDF vectorization, cosine similarity between sentence pairs, and a `similarity_search()` function that mirrors the RAG retrieval pipeline

**Topics Covered:**
- Text converted to fixed-size numerical vectors
- Cosine similarity for measuring semantic closeness
- Top-K similarity search by score
- Role of embeddings in RAG: find relevant context before passing to the LLM

**Model/Libraries:** TF-IDF via scikit-learn (Python 3.14-compatible; used as a dependency-free alternative to the OpenAI embeddings API)

**Setup:**
```bash
cd Step_4_Embeddings
pip install -r requirements.txt
cp .env.example .env
```

---

### ✅ Step 5: RAG (Retrieval-Augmented Generation)
*Status: Complete*

Combine retrieval with generation to build an agent that answers questions grounded in external documents — not hallucinated knowledge.

**Notebooks:**
- `step5_rag.ipynb` — Full end-to-end RAG pipeline: document loading, chunking, embedding, vector search, context injection, and LLM generation

**Topics Covered:**
- Document loading and chunking with `pypdf`
- Embedding chunks with `sentence-transformers`
- Storing and searching vectors with ChromaDB
- Injecting retrieved context into the LLM prompt to ground responses
- Full pipeline: chunk → embed → store → retrieve → generate

**Tools/Libraries:** `pypdf`, `sentence-transformers`, `chromadb`, `groq`  
**Model:** `llama-3.3-70b-versatile` via Groq

**Setup:**
```bash
cd Step_5_RAG
pip install -r requirements.txt
cp .env.example .env
# Add your Groq API key to .env
```

---

## 🎯 What You'll Learn

| # | Concept | Status |
|---|---------|--------|
| 1 | How LLMs work — training, tokenization, RLHF, limitations | ✅ Complete |
| 2 | Calling LLM APIs and building multi-turn applications | ✅ Complete |
| 3 | Tool calling, JSON schemas, and the agent decision loop | ✅ Complete |
| 4 | Embeddings, cosine similarity, and vector search | ✅ Complete |
| 5 | Full RAG pipeline: retrieval + generation + grounded answers | ✅ Complete |

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or JupyterLab
- A [Groq API key](https://console.groq.com/) — free tier is sufficient for all steps

### Installation

```bash
# Clone the repo
git clone https://github.com/zara-shahid/AI-Agents-from-Scratch.git
cd AI-Agents-from-Scratch

# Navigate to any step
cd Step_3_Tool_Calling  # or Step_2, Step_4, Step_5

# Install dependencies
pip install -r requirements.txt

# Set up your environment
cp .env.example .env
# Open .env and add your Groq API key

# Launch Jupyter
jupyter notebook
```

Start with **Step 1** and work through each step in order.

---

## 💡 Learning Path

**New to LLMs?**
1. Read the Step 1 section and watch Karpathy's video
2. Complete the DeepLearning.AI prompt engineering course
3. Work through Step 2 notebooks interactively — build the Meeting Notes Extractor
4. Move to Step 3 for tool calling and the agent loop
5. Step 4 for embeddings and similarity search
6. Step 5 to tie everything together with a full RAG pipeline

**Already familiar with LLMs?**
1. Start at Step 2 for API patterns and multi-turn conversation management
2. Step 3 for tool calling — this is where agents actually start to take shape
3. Steps 4 and 5 for memory and retrieval

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.8+ | Core language |
| Jupyter Notebooks | Interactive learning environment |
| Groq API | LLM inference (fast, free tier) |
| LLaMA 3.3-70B (via Groq) | Underlying model for Steps 2–5 |
| scikit-learn | TF-IDF vectorization (Step 4) |
| sentence-transformers | Semantic embeddings (Step 5) |
| ChromaDB | Vector store for RAG (Step 5) |
| pypdf | Document loading and chunking (Step 5) |
| wttr.in | Live weather data for tool calling demo (Step 3) |
| python-dotenv | Secure API key management |

---

## 📖 Key Concepts

**Context Window**
Everything the model knows lives inside its context window. No memory exists outside of it — which is exactly why agents need external memory tools like vector stores.

**Tokenization**
LLMs process tokens (chunks of characters), not words. This affects prompt design and is why character-level tasks are harder for models than they seem.

**Tool / Function Calling**
Models can invoke external functions to fetch live data, run calculations, or interact with systems. This is the foundational mechanism of AI agents — the point where an LLM stops being a chatbot and becomes something that can act.

**Agent Loop**
```
Observe → Think → Act → Update → Repeat
```
1. **Observe** — Read current state / conversation
2. **Think** — Decide what action to take
3. **Act** — Call a tool or generate a response
4. **Update** — Add results back to context
5. **Repeat** — Continue until goal is reached

**RAG (Retrieval-Augmented Generation)**
Instead of relying on what the model memorized during training, RAG retrieves relevant context from an external document store and injects it into the prompt — grounding the model's response in real, up-to-date information.

---

## 🙏 Acknowledgments

- **Andrej Karpathy** — His *Intro to Large Language Models* video remains the clearest explanation of how LLMs actually work from first principles. Step 1 of this repo is built around it.
- **DeepLearning.AI** — The *ChatGPT Prompt Engineering for Developers* short course is a focused, practical introduction to prompt design that translates directly to agent development.
- **Groq** — For making `llama-3.3-70b-versatile` inference fast and accessible on a free tier — critical for iterating quickly across all steps without worrying about API costs.
- **Meta AI** — For open-sourcing the LLaMA model family that powers everything from Step 2 onward.
- **LangChain** — For the RAG tutorials and documentation that informed the Step 5 pipeline design.
- **Pixegami** — For the concise RAG walkthrough video that made the Step 5 architecture immediately concrete.
- The open-source ML community — For `sentence-transformers`, `ChromaDB`, `scikit-learn`, and every other tool that makes self-directed learning at this level possible.

---

## 📝 License

This repository is open source under the [MIT License](LICENSE).

---

## 📞 Questions or Feedback?

- Open an issue in the repository
- Check the individual step READMEs for deeper context
- Review notebook comments for inline explanations

---

**Built with curiosity. Documented step by step. 🚀**
