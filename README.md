# 🧠 ConFeval: Calibrated Fine-Tuning & Faithfulness Evaluation for LLMs  
**Author:** Aditi Prabakaran  
**Affiliations:** Undergraduate Research Intern @ IIIT-Hyderabad · B.Tech CSE @ SRM University (2027)  
[GitHub Repository](https://github.com/Aditi2k5/confeval)

---

## 🔍 Overview  
**ConFeval** (Confidence-Faithfulness Evaluation) is a research-oriented framework designed to enhance the **faithfulness**, **confidence calibration**, and **interpretability** of Large Language Models (LLMs).  

This project explores *parameter-efficient fine-tuning (PEFT)* and *Low-Rank Adaptation (LoRA)* under quantization to improve model self-awareness and reduce hallucinations — making models not just *accurate*, but also *trustworthy*.

It evaluates models such as `google/gemma-2-2b-it` and `microsoft/phi-2` before and after **targeted data augmentation (DA)** to assess how fine-tuning affects factual consistency and calibration.

---

## 🎯 Motivation  
Modern LLMs often produce *confidently incorrect* or *plausible but false* responses — a challenge in domains that demand high factual reliability.  
ConFeval aims to measure and mitigate such issues by integrating **faithfulness evaluation** and **confidence calibration** into fine-tuning workflows.  

The research explores how **data-aware fine-tuning** improves truthfulness while maintaining semantic coherence.

---

## 🧩 Key Features  
- 🔧 **PEFT + LoRA Quantized Fine-Tuning** — lightweight, memory-efficient model adaptation  
- 📊 **Confidence & Faithfulness Metrics** — evaluates model truthfulness, ECE, and BERTScore F1  
- 🧮 **Case-Level Error Analysis** — tracks under/over-confidence, hallucination, and correction patterns  
- 🌀 **Sequential Learning Pipeline** — multi-stage adaptation (base → aligned → faithful model)  
- ⚡ **Targeted Data Augmentation** — enriches training sets to reinforce factual correctness  

---

## 📊 Sample Results  

### 🔹 `google/gemma-2-2b-it`
| Metric | Base | Post-DA | Δ (%) |
|:--|:--:|:--:|:--:|
| **Faithfulness** | 0.3593 | **0.5381** | +49.75 ↑ |
| **BERTScore F1** | 0.8410 | **0.8582** | +2.04 ↑ |
| **ECE (↓)** | 0.0252 | **0.0374** | +48.3 ↑ |
| **Mean Confidence** | 0.8159 | **0.8713** | +6.8 ↑ |
| **Over-confident Errors** | 14 | **7** | −50 ↓ |

---

### 🔹 `microsoft/phi-2`
| Metric | Base | Post-DA | Δ (%) |
|:--|:--:|:--:|:--:|
| **Faithfulness** | 0.3395 | **0.3608** | +6.26 ↑ |
| **BERTScore F1** | 0.7974 | **0.8319** | +4.33 ↑ |
| **ECE (↓)** | 0.0688 | **0.0588** | −14.49 ↓ |
| **Mean Confidence** | 0.7768 | **0.8546** | +10.01 ↑ |

🧭 **Summary:**  
Faithfulness improvements of up to **+49%**, BERTScore F1 increase of **+4%**, and a 50% reduction in over-confident errors show how *targeted fine-tuning improves both reliability and calibration*.

---

## ⚙️ Installation & Usage  

```bash
# Clone the repository
git clone https://github.com/Aditi2k5/confeval.git
cd confeval

# Install dependencies
pip install -r requirements.txt

# Launch the Jupyter notebook for interactive analysis
jupyter notebook llm_faithfulness_targeted_da.ipynb

