# Lexical-Simplification-Static-and-Contextual-Embeddings-
Lexical Simplification study comparing static embeddings (Word2Vec + POS filtering) with deep learning (BERT MLM + Mistral-7B) for Substitution Generation and Selection. Evaluated on the MLSP 2024 dataset using Potential@k, Recall@k, and Precision@k.
## Overview

This study investigates two tasks of the **Lexical Simplification (LS) pipeline** — *Substitution Generation (SG)* and *Substitution Selection (SS)*.  

- For **SG**, we compare **Word2Vec with POS filtering** against a deep learning-based approach using **BERT Masked Language Modeling (MLM)**.  
- For **SS**, we apply **cosine similarity** to rank Word2Vec-generated candidates and a **decoder-only LLM** to rank MLM-generated candidates through prompt-based selection.  

Experiments use the **[MLSP 2024 Shared Task dataset](https://huggingface.co/datasets/MLSP2024/MLSP2024)**. Evaluation metrics include **Potential@k, Recall@k, and Precision@k**.  

Results show that **MLM-based candidates consistently outperform Word2Vec-based candidates** across all three metrics, highlighting the promise of contextual language models for lexical simplification.
