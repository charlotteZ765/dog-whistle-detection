# Decoding Dog Whistles with LLMs

This repo accompanies the project **“Decoding Dog Whistles: LLMs and the Detection of Covert Harmful Speech.”**

Key findings are presented in [final report](./QTM340_Final_Report.pdf).

We study how well large language models detect and interpret *political dog whistles*—terms that seem neutral to most people but carry harmful coded meanings to specific groups.

---

## Overview

We evaluate four LLMs on two main tasks:

1. **Dog Whistle Detection**
   - Is a dog whistle present?
   - Which term is the dog whistle?
   - How well does the model define it (via SBERT cosine similarity)?

2. **Dog Whistle Disambiguation**
   - Given a dog whistle keyword and its coded meaning, decide whether a sentence uses it in a *coded* or *non-coded* way.

---

## Models

- **DeepSeek R1 Distilled Llama 70B**
- **Llama 3.3 70B Instruct Turbo**
- **Llama 3.2 11B Vision Turbo**
- **Gemini 2.0 Flash**

**Gemini 2.0 Flash** generally performs best across detection, definition, and disambiguation.

---

## Data

- **Detection dataset**
  - 50 positive (coded) examples
  - 50 negative examples (25 innocuous uses of the keyword, 25 with no keyword)

- **Disambiguation dataset**
  - 124 examples total
  - 13 dog whistle keywords, each with both coded and non-coded usages

Datasets are derived from the Silent Signals Corpus and dog whistle glossaries in prior work. :contentReference[oaicite:1]{index=1}

---

## Key Findings

- Few-shot prompting improves performance for all models.
- Models often **over-flag** non-coded uses when inflammatory language is present.
- Rare or very obscure dog whistles remain hard to detect.
- Main challenge: understanding **context and intent**, not just keyword spotting.

---

## Limitations

- Overall F1 scores are moderate (≈0.63–0.79).
- Synthetic data may not fully represent real-world online speech.
- Few-shot prompts can be expensive to run at scale.

---
