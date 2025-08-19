# 🧠 Multi-Agent GenAI Framework for Reducing Hallucination & Enhancing Reasoning of LLMs for DSA Problems.

This project presents a **multi-agent framework** designed to mitigate hallucinations in Large Language Models (LLMs) and enhance their reasoning capabilities. Using **Gemini API** and **n8n (workflow automation)**, the system simulates collaboration between multiple agents — **Creator, Critic, Verifier, and Refiner** — to solve **Data Structures & Algorithms (DSA)** problems with higher factual correctness and reliability.  

The framework was tested on a **Kaggle-based DSA dataset** and achieved measurable improvements in factual accuracy, demonstrating the potential of multi-agent orchestration in trustworthy AI systems.  

---

## 🚀 Features
- **Dataset-Driven Evaluation**: Uses a Kaggle DSA dataset with ground-truth answers for benchmarking hallucinations.  
- **Multi-Agent Architecture**:
  - **Creator**: Generates initial solution using Gemini API.  
  - **Critic**: Evaluates logical accuracy and completeness.  
  - **Verifier**: Cross-checks outputs against ground truth.  
  - **Refiner**: Improves responses and reduces hallucination.  
- **Automated Orchestration in n8n**:
  - Visual no-code workflow implementation.  
  - Agents chained through decision/control nodes.  
  - Integrated API calls via HTTP request nodes.  
- **Evaluation Metrics**:
  - Accuracy Gain ✅  
  - Time Complexity ⏱️  
  - Space Complexity (Token growth) 📈  

---

## 📊 Dataset
- **Source**: [DSA Questions Dataset – Kaggle](https://www.kaggle.com/datasets/inductiveanks/dsa-questions-dataset) Modified this dataaset according to my project.  
- **Format**: JSON/CSV with fields such as *question, category, Ground truth answer, Best Time Complexity, Best Space Complexity.*.  
- **Preprocessing**: Normalization, ambiguity filtering for consistency.  

---

## 🔄 Workflow (n8n Proof-of-Concept)
The entire framework was implemented in **n8n**, where each agent is a modular node or sequence of nodes.  

**Workflow Chain**:  Creator → Critic → Verifier → Refiner → Metric Agent → Dataset Automation for capturing the data of each agent 
(for future work).
---

## ⚙️ Technical Implementation
- **Backend Automation**: Orchestrated using **n8n**, eliminating need for Node.js/Flask.  
- **API Integration**: Gemini 2.5 Flash API for LLM reasoning.  
- **Decision Flow**: `IF/Switch` nodes to handle correctness checks.  
- **Scoring**: Outputs logged and benchmarked against ground truth Dataset referenced from kaggle.  

---

## 📈 Evaluation Results
We manually annotated outputs across DSA queries and measured:  

- **Hallucination Reduction**:  
  - Refiner improved factual correctness by **20%+** compared to Creator alone.  
- **Trade-offs**:  
  - Slight increase in latency (1.2–1.5x).  
  - Growth in token size due to reasoning propagation.  
- **Key Insight**: Modular multi-agent reasoning consistently outperformed single-prompt responses.  

*(Insert result charts, e.g., Creator vs Refiner correctness pie charts)*  

---

## 📝 Key Observations
- ✅ Multi-agent reasoning **reduces hallucination** and improves factual correctness.  
- ✅ Modular architecture (generation, critique, verification, refinement) yields **coherent & grounded responses**.  
- ⚠️ Trade-offs: Latency & token growth are introduced but remain manageable.  
- ⚡ n8n enabled **rapid prototyping** and easy orchestration without traditional backend coding.  

---

## 📂 Repository Structure
- README.md # Project documentation
- workflow.json # n8n exported workflow (multi-agent pipeline)
- workflow.png # Workflow diagram (screenshot)
- results/ # Evaluation charts & sample outputs


---

## 🌟 Impact
This project validates the **feasibility of multi-agent GenAI frameworks** in solving hallucination and reliability challenges in AI. By combining **agent orchestration + dataset-driven evaluation**, we built a **self-correcting pipeline** for educational content generation — a model that can be extended to other high-stakes domains.  

---

## 📌 Future Directions
- Integration with **RAG (Retrieval-Augmented Generation)** pipelines.  
- Expansion to larger datasets and domains beyond DSA.  
- Deployment of real-time monitoring and **LLM observability dashboards**.  

---

