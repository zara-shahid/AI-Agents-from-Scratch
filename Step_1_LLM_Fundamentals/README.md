# Step 1: LLM Fundamentals

Before building AI agents, I studied how Large Language Models actually work under the hood - not just how to use them, but what they are and why they behave the way they do.

---

## Resources

| Resource | Type | Link |
|---|---|---|
| Intro to Large Language Models | Video (Andrej Karpathy) | [YouTube](https://www.youtube.com/watch?v=zjkBMFhNj_g) |
| ChatGPT Prompt Engineering for Developers | Course (DeepLearning.AI) | [deeplearning.ai](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) |

---

## Key Concepts Learned

### How LLMs Work
- LLMs are next-token predictors trained on massive text datasets
- Training compresses internet-scale text into billions of parameters (a "lossy zip file" of the internet)
- The model does not retrieve information - it reconstructs it from learned patterns
- Two stages: **pre-training** (learn language from raw text) and **fine-tuning** (align to follow instructions)

### Tokenization
- LLMs do not read words - they read **tokens** (chunks of characters)
- The same word can be multiple tokens; numbers and code tokenize differently than prose
- This is why LLMs struggle with character-level tasks like counting letters or reversing words

### Context Window
- Everything the model knows in a conversation is inside its **context window**
- The model has no memory outside of what is currently in the context
- This limitation is one of the core reasons agents need external memory tools

### RLHF (Reinforcement Learning from Human Feedback)
- Raw pre-trained models predict text but do not follow instructions reliably
- RLHF fine-tunes the model to be helpful, harmless, and honest
- This is what turns a "document completer" into an "assistant"

### Prompting Techniques
- **Zero-shot**: ask directly with no examples
- **Few-shot**: provide examples in the prompt to guide the output format
- **Chain of thought**: ask the model to think step by step before answering
- **System vs user roles**: system prompt sets behavior, user prompt is the actual request
- **Delimiters**: use `###`, `"""`, or XML tags to clearly separate instructions from content
- Output format control: asking for JSON, markdown, or structured output

### Why This Matters for Agents
- Agents are LLMs that take actions in a loop - but the core reasoning still happens inside the model
- Understanding context windows explains why agents need memory systems
- Understanding tokenization explains why careful prompt design matters
- Prompting techniques learned here are used directly when writing agent system prompts

---

## Key Takeaway

> An LLM is not a search engine and not a database. It is a reasoning engine trained to predict what comes next. Building agents means giving that reasoning engine the ability to take actions - but the quality of those actions depends entirely on how well you understand the model underneath.

---

*Next: [Step 2 - LLM APIs](../Step_2_LLM_API_Fundamentals/)*
