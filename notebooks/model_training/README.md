# Model Training Notebooks

End-to-end model training and evaluation for NER on the Naamapadam dataset.

## Notebooks

| Notebook | Language | Cells | Models Covered |
|----------|----------|-------|----------------|
| `NER_Hindi.ipynb` | Hindi | 135 | Classic + LLMs + Few-Shot |
| `NER_Bengali_Train.ipynb` | Bengali | 18 | Classic models |
| `NER_Telugu_Train.ipynb` | Telugu | 17 | Classic models |

---

## NER_Hindi.ipynb — Most Comprehensive

This notebook is the centerpiece of the project. It covers three major experiments:

### Part 1: Classic NLP Models
Fine-tuned token classification / seq2seq models:
- `t5-base` — Token classification via seq2seq generation
- `google/flan-t5-base` — Instruction-tuned seq2seq
- `google/mt5-small` — Multilingual T5
- `bert-base-multilingual-cased` (mBERT) — Encoder with token classification head
- `xlm-roberta-base` (XLM-R) — Cross-lingual encoder

### Part 2: LLM Fine-Tuning (LoRA / PEFT)
Modern generative LLMs adapted for Hindi NER via:
- `TinyLlama/TinyLlama-1.1B-Chat-v1.0`
- `meta-llama/Llama-3.2-1B`
- `google/gemma-2b` (Gemma-2)
- `google/gemma-3-1b-it` (Gemma-3)
- `Qwen/Qwen2.5-0.5B`
- `microsoft/Phi-2`
- `mistralai/Mistral-7B-Instruct-v0.2`

### Part 3: Few-Shot Inference (0–5 Shots)
In-context learning evaluation across 9 models:
- Gemma3-1b-it (best: 19.05% F1 at 5-shot)
- Navarasa2.0 / Indic-Gemma-2B (best: 16.00% F1 at 5-shot)
- TinyLlama, Llama-3.2-1B, Qwen2.5-0.5B, T5-base, FlanT5, mT5-small, Phi-2

### Sampling Strategy
Entity-aware hybrid sampling (2000 train, 50 val):
- 50% random + 50% entity-stratified
- Ensures rare entity types (ORG) are adequately represented

---

## NER_Bengali_Train.ipynb & NER_Telugu_Train.ipynb

Same architecture as Hindi Part 1 (classic models), adapted for:
- Bengali (`bn`) — mBERT best F1: **54.63%**, XLM-R best F1: **60.61%**
- Telugu (`te`) — mBERT best F1: **63.49%**, XLM-R best F1: **66.15%**

---

## GPU Requirements

| Experiment | Min VRAM | Recommended |
|------------|----------|-------------|
| Classic models (mBERT, XLM-R) | 8 GB | 16 GB |
| LLM fine-tuning (≤2B params) | 16 GB | 24 GB (A100) |
| LLM fine-tuning (7B params) | 24 GB | 40 GB A100 |
| Few-shot inference (≤2B) | 8 GB | 16 GB |

> All experiments were run on **Google Colab Pro (A100 / V100)**.
