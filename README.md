# Medical NER & Causal Relation Extraction  
**Academic Project — 6th Semester**

## Project Overview
This project develops an **advanced Medical Named Entity Recognition (NER)** system that accurately identifies and classifies **chemical** and **disease** entities in biomedical literature. In addition to entity extraction, the system determines **whether a causal relationship exists** between extracted entities and characterizes the **nature** of those causal relations.

The goal is to enable precise biomedical information extraction to support downstream applications such as clinical decision support, literature curation, drug safety surveillance, and biomedical research.

---

## Key Objectives
- Build a robust NER module tailored to biomedical text that recognizes:
  - Chemical entities (drugs, compounds, reagents)
  - Disease/condition entities (diseases, syndromes, clinical outcomes)
- Design and implement a relation extraction module that:
  - Detects causal links between entity pairs
  - Classifies the relation type (e.g., *causes*, *prevents*, *associated_with*, *no_relation*)
- Ensure the pipeline is modular, reproducible, and suitable for further research or integration.

---

## Features
- Domain-specific NER optimized for biomedical vocabulary and acronyms
- Relation classification to detect and label causal interactions
- Preprocessing and normalization for noisy scholarly text (abbreviations, chemical names)
- Evaluation scripts for standard metrics: Precision, Recall, F1 (entity-level & relation-level)
- Reproducible training & inference pipeline (config-driven)

---

## Method (High-level)
1. **Text preprocessing**: tokenization, sentence segmentation, acronym expansion, and entity normalization.  
2. **NER model**: Transformer-based (e.g., BioBERT / ClinicalBERT / PubMedBERT) fine-tuned for BIO-tagging on chemical and disease labels.  
3. **Entity linking / normalization** (optional): map recognized mentions to identifiers where available (e.g., MeSH, ChEBI).  
4. **Relation extraction**: a classifier (pairwise or joint model) that takes entity spans and context to predict causal vs non-causal relations and relation type.  
5. **Post-processing**: filter/prioritize high-confidence relations, aggregate duplicate mentions.

---

## Dataset & Evaluation
- Use relevant biomedical corpora (examples): BC5CDR, ChemProt, or curated in-house datasets.  
- Recommended splits: train / validation / test following standard benchmarks.  
- Evaluation metrics:
  - Entity-level: Precision, Recall, F1 (span-level, exact match)
  - Relation-level: Precision, Recall, F1 (requires correct entity spans + relation label)

---

## Technologies & Tools
- Python 3.8+  
- Transformers (Hugging Face) — Bio/Clinical pretrained models  
- PyTorch or TensorFlow (training backend)  
- SpaCy / NLTK (preprocessing utilities)  
- Scikit-learn (evaluation utilities)  
- Optional: Docker for reproducible environments

