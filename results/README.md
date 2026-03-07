# Results

## Plots

| File | Description |
|------|-------------|
| `plots/classic_model_comparison.png` | T5/FlanT5/mT5/mBERT/XLM-R on Hindi, Bengali, Telugu |
| `plots/llm_finetuning_hindi.png` | 6 LLMs fine-tuned on Hindi NER (Precision/Recall/F1) |
| `plots/few_shot_analysis.png` | 0–5 shot F1 line curves + model×shot heatmap |
| `plots/cross_language_performance.png` | mBERT vs XLM-R bar chart + radar chart across 3 languages |
| `plots/full_model_landscape_hindi.png` | All 14+ models ranked by F1, color-coded by architecture type |

## Metrics (CSV)

| File | Rows | Columns |
|------|------|---------|
| `metrics/hindi_results.csv` | 12 models | Model, Type, Precision, Recall, F1 |
| `metrics/bengali_results.csv` | 6 models | Model, Type, Precision, Recall, F1 |
| `metrics/telugu_results.csv` | 6 models | Model, Type, Precision, Recall, F1 |
| `metrics/hindi_fewshot_results.csv` | 48 rows (8 models × 6 shots) | Model, Shots, Precision, Recall, F1 |

## Quick Summary

### Best Models Per Language

| Language | Best Model | F1 Score |
|----------|------------|----------|
| Hindi | mBERT | 67.49% |
| Bengali | XLM-R | 60.61% |
| Telugu | XLM-R | 66.15% |

### Best LLM Fine-Tuned (Hindi)

| Model | F1 Score |
|-------|----------|
| Mistral-7B | 59.10% |
| Gemma-2-2B | 51.99% |
| Llama-3.2-1B | 46.22% |

### Best Few-Shot (Hindi, 5-shot)

| Model | F1 Score |
|-------|----------|
| Gemma3-1b-it | 19.05% |
| Navarasa2.0 | 16.00% |
| T5-base | 6.78% |
