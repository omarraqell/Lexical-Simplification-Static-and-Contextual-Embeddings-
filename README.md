# Lexical-Simplification-Static-and-Contextual-Embeddings-
Lexical Simplification study comparing static embeddings (Word2Vec + POS filtering) with deep learning (BERT MLM + Mistral-7B) for Substitution Generation and Selection. Evaluated on the MLSP 2024 dataset using Potential@k, Recall@k, and Precision@k.
## Overview

This study investigates two tasks of the **Lexical Simplification (LS) pipeline** — *Substitution Generation (SG)* and *Substitution Selection (SS)*.  

- For **SG**, we compare **Word2Vec with POS filtering** against a deep learning-based approach using **BERT Masked Language Modeling (MLM)**.  
- For **SS**, we apply **cosine similarity** to rank Word2Vec-generated candidates and a **decoder-only LLM** to rank MLM-generated candidates through prompt-based selection.  

Experiments use the **[MLSP 2024 Shared Task dataset](https://huggingface.co/datasets/MLSP2024/MLSP2024)**. Evaluation metrics include **Potential@k, Recall@k, and Precision@k**.  

Results show that **MLM-based candidates consistently outperform Word2Vec-based candidates** across all three metrics, highlighting the promise of contextual language models for lexical simplification.
## Results

### Substitution Generation (SG)

| Method   | Potential@10 | Precision@10 | Recall@10 |
|----------|--------------|--------------|-----------|
| Word2Vec | 0.442        | 0.072        | 0.115     |
| MLM      | **0.577**    | **0.098**    | **0.201** |

The MLM generator clearly outperforms Word2Vec across all metrics, showing the importance of contextual embeddings for generating substitutes.

---

### Substitution Selection (SS)

| Method                      | Potential@p | Precision@p | Recall@p |
|-----------------------------|-------------|-------------|----------|
| Word2Vec Context-Ranking    | **0.334**   | **0.113**   | **0.095** |
| Prompt-based (Mistral-7B)   | 0.208       | 0.021       | 0.045    |

The Word2Vec semantic similarity ranker achieved higher scores overall, while the Mistral selector sometimes hallucinated or failed to return valid candidates.
