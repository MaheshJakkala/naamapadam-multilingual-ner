# Data Analysis Notebooks

Exploratory Data Analysis (EDA) for all 7 Indic languages in the Naamapadam NER dataset.

## Notebooks

| Notebook | Language | Script | HF Code | Cells |
|----------|----------|--------|---------|-------|
| `Assamese.ipynb` | Assamese | অসমীয়া | `as` | 31 |
| `NER_Bengali_DA.ipynb` | Bengali | বাংলা | `bn` | 74 |
| `ner_hindi_DA.ipynb` | Hindi | हिन्दी | `hi` | 63 |
| `ner_marathi_DA.ipynb` | Marathi | मराठी | `mr` | 63 |
| `ner_oriya.ipynb` | Odia | ଓଡ଼ିଆ | `or` | 44 |
| `Tamil_NER.ipynb` | Tamil | தமிழ் | `ta` | 65 |
| `Telugu.ipynb` | Telugu | తెలుగు | `te` | 34 |

## What Each Notebook Contains

Each EDA notebook covers:

1. **Dataset loading** via HuggingFace `datasets` library
2. **Split statistics** — train/validation/test sizes
3. **Token length distribution** — histogram of sentence lengths
4. **Entity type distribution** — PER/ORG/LOC counts and proportions
5. **BIO tag distribution** — B- vs I- tag ratios
6. **Entity density analysis** — % of tokens that are named entities
7. **Word clouds** (language-specific)
8. **Co-occurrence analysis** — entity type co-occurrence heatmaps
9. **Sample sentence visualization** with entity highlighting

## Dataset Loading

```python
from datasets import load_dataset

# Replace the language code as needed
ds = load_dataset("ai4bharat/naamapadam", "hi")  # Hindi
ds = load_dataset("ai4bharat/naamapadam", "bn")  # Bengali
ds = load_dataset("ai4bharat/naamapadam", "te")  # Telugu
ds = load_dataset("ai4bharat/naamapadam", "ta")  # Tamil
ds = load_dataset("ai4bharat/naamapadam", "mr")  # Marathi
ds = load_dataset("ai4bharat/naamapadam", "or")  # Odia
ds = load_dataset("ai4bharat/naamapadam", "as")  # Assamese
```
