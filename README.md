# Nexora – The AI That Codes, Thinks, and Learns From Its Own Mistakes

> “An intelligent, modular AI system that plans, codes, validates, and refines itself — powered by a fine-tuned TinyLlama model.”

![Nexora Banner](https://via.placeholder.com/1000x250?text=Nexora+AI+Assistant)

---

## 🏷️ Badges

![Python](https://img.shields.io/badge/Python-3.11%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.50%2B-ff4b4b)
![Ollama](https://img.shields.io/badge/Ollama-Local%20LLM-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Build-Passing-success)

---

## 🚀 Overview

**Nexora** is an experimental **multi-agent AI assistant** built to explore the intersection of *autonomous reasoning*, *code generation*, and *self-improvement*.

Developed as a personal R&D project, Nexora can:

- 🧩 Understand complex prompts  
- 🧭 Plan multi-step actions  
- 💻 Generate, test, and refine code  
- 📚 Conduct factual research  
- 📊 Measure its own reasoning complexity through **entropy tracking**

Built with **Python**, **Streamlit**, and a **fine-tuned TinyLlama model**, Nexora operates fully **offline** via **Ollama**, ensuring privacy, speed, and local inference.



## 🧱 Project Structure

<details>
<summary>Click to expand</summary>

```plaintext
assistant_hub/
│
├── streamlit_app.py              # Main UI entry point
├── run_assistant.py              # Initializes backend + agents
│
├── core/                         # Core coordination layer
│   ├── config.py
│   ├── factory.py
│   ├── dependency_injector.py
│   └── agent_coordinator.py
│
├── agents/                       # Specialized LLM-driven agents
│   ├── proxy_agent.py
│   ├── planner_agent.py
│   ├── researcher_agent.py
│   ├── coder_agent.py
│   ├── validator_agent.py
│   └── code_validation_loop.py
│
├── tools/                        # Execution helpers and utilities
│   ├── coding_tools.py
│   ├── output_formatter.py
│   └── langchain_tools.py
│
├── ui/                           # Streamlit UI logic
│   ├── helpers.py
│   └── views.py
│
├── models/                       # Fine-tuned TinyLlama GGUF model
│   └── tinyllama-codegen-q4_k_m.gguf
│
├── training/                     # LoRA fine-tuning scripts + datasets
│   ├── fine_tuning_manager.py
│   ├── collector.py
│   └── datasets/
│
└── reports/                      # Metrics, logs, and presentation
    ├── entropy_tracking_simulation.csv
    └── Nexora_Presentation_Script.docx
````

</details>

---

## ⚙️ Core Features

| Feature                         | Description                                                                                            |
| ------------------------------- | ------------------------------------------------------------------------------------------------------ |
| 🤖 **Multi-Agent Intelligence** | Planner, Researcher, Coder, and Validator agents collaborate autonomously.                             |
| 🧠 **Fine-Tuned Model**         | Based on `TinyLlama/TinyLlama-1.1B-Chat-v1.0`, fine-tuned with **LoRA + Unsloth** on *CodeAlpaca-20k*. |
| 💻 **Offline Inference**        | Runs fully local in GGUF format (`q4_k_m`) via **Ollama**.                                             |
| 📈 **Entropy Tracking**         | Monitors task refinement, time, and “frustration” to analyze reasoning complexity.                     |
| 💬 **Interactive UI**           | Streamlit interface with chat memory, file uploads, and audio transcription.                           |
| 🔊 **Voice & File Support**     | Upload audio, documents, or code directly into the interface.                                          |

---

## 🧠 Fine-Tuning Journey

| Step               | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| 🧩 **Base Model**  | TinyLlama/TinyLlama-1.1B-Chat-v1.0                                     |
| 🧰 **Dataset**     | sahil2801/CodeAlpaca-20k                                               |
| 🧮 **Method**      | LoRA fine-tuning with Unsloth                                          |
| ☁️ **Environment** | Google Colab (T4 GPU)                                                  |
| 🧠 **Output**      | LoRA adapter (~45 MB) merged into TinyLlama                            |
| 💾 **Format**      | GGUF (q4_k_m) for Ollama                                               |
| ⚙️ **Result**      | Locally running fine-tuned model optimized for code and planning tasks |

---

## 🧪 Entropy Tracking (Experimental)

Every research or code-generation session logs:

* Task Description
* Number of Refinements
* Time Spent
* Errors Encountered
* Frustration Score

**Example report:**

| Task                   | Refinements | Time (min) | Errors | Frustration |
| ---------------------- | ----------- | ---------- | ------ | ----------- |
| Research AI Regulation | 4           | 11.0       | 2      | 5           |
| Climate Impact Study   | 2           | 6.0        | 0      | 2           |
| Code Debugging Loop    | 5           | 12.5       | 3      | 6           |

These metrics help visualize how “uncertain” or complex each task becomes — a measure of **AI entropy**.

---

## 💻 Installation & Setup

### 🧩 1. Clone Repository

```bash
git clone https://github.com/yourusername/nexora.git
cd nexora
```

### 🧰 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```

### 📦 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 🧠 4. Run Streamlit App

```bash
streamlit run assistant_hub/streamlit_app.py
```

### ⚙️ 5. (Optional) Load Fine-Tuned Model

```bash
ollama pull tinyllama-codegen
```

Then reference your `.gguf` model file inside `assistant_hub/models/`.

---

## 🎥 Demo

📹 **[Watch Nexora in Action](#)**

> “Can an AI truly learn from its own mistakes?”
> Nexora plans, codes, and refines its own solutions — autonomously and offline.

---

## 🧰 Tech Stack

| Category           | Tools & Frameworks         |
| ------------------ | -------------------------- |
| 💻 **Language**    | Python 3.11+               |
| 🎨 **Frontend**    | Streamlit 1.50+            |
| 🤖 **Modeling**    | TinyLlama + LoRA + Unsloth |
| ⚙️ **Inference**   | Ollama (GGUF local LLM)    |
| 🔗 **Integration** | LangChain / Custom Tools   |

---

## 🔭 Future Improvements

* 🧠 Integrate RAG (Retrieval-Augmented Generation) for dynamic research
* 📊 Build visual dashboard for entropy metrics
* 🧩 Add continuous fine-tuning pipeline from collected data
* 👥 Enable collaborative multi-user sessions
* 🧰 Add plugin system for custom external tools

---

## 👤 Author

**Ayanda [Your Surname]**
💼 AI Engineer | ML Developer | Indie Researcher
📫 [LinkedIn](#) • [Portfolio](#) • [Email](#)

> *“I build AI systems that learn to think.”*

---

## 📜 License

This project is open-source and available under the **MIT License**.

---

## 🌟 Acknowledgments

* **TinyLlama** team for the efficient open-source model
* **sahil2801/CodeAlpaca-20k** for dataset inspiration
* **Unsloth** for simplifying LoRA fine-tuning
* **Streamlit** for enabling rapid, beautiful interfaces

---

## 🧭 Support the Project

If you find **Nexora** inspiring, give it a ⭐ on GitHub and share your ideas or contributions!
