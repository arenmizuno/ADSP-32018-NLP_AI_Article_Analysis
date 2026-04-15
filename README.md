# ADSP 32018 – Natural Language Processing
## Final Project: AI Article Analysis

**University of Chicago**  
**Instructor:** Ignas Grabauskas  
**Term:** Winter 2026  

---

## Overview
This repository contains my final project for *ADSP 32018: Natural Language Processing*, a course focused on extracting insights from unstructured text using modern NLP techniques.

The course explored the forefront of Natural Language Processing through Transformer architectures and large language models. Key topics included classification, question answering, and text generation, progressing from foundational methods to deep learning approaches. Additional emphasis was placed on fine-tuning LLMs, prompt engineering, retrieval-augmented generation (RAG), and agentic AI systems. All work was implemented in Python using libraries such as PyTorch and the Hugging Face ecosystem.

This project applies these concepts to a large-scale real-world dataset of AI-related news articles, building an end-to-end NLP pipeline for structured analysis.

---

## Final Project
**Description:**  
This project analyzes approximately 200,000 AI-related news articles to understand how artificial intelligence is discussed across industries, companies, and technologies.

The project builds a full NLP pipeline that integrates topic modeling, entity extraction, and sentiment analysis to generate structured insights from unstructured news data.

---

### Methodology

- Performed **data cleaning and preprocessing**:
  - Removed duplicates, noise, and outliers  
  - Preserved punctuation and capitalization for NER  
  - Filtered low-information articles using word frequency thresholds  

- Conducted **topic modeling using multiple approaches**:
  - **LDA** (probabilistic topic modeling)  
  - **NMF** (matrix factorization with TF-IDF)  
  - **BERTopic** (embedding-based clustering)  
  - Selected **BERTopic on text** as the final model due to strongest semantic coherence  

- Built **Named Entity Recognition (NER) pipeline**:
  - Extracted companies using spaCy (`en_core_web_lg`)  
  - Filtered and ranked entities to reduce noise  
  - Extracted technologies using PhraseMatcher and curated lists  

- Trained **sentiment analysis model**:
  - Model: DistilRoBERTa  
  - Dataset: ML News Sentiment Dataset  
  - Achieved balanced performance (~0.87 F1 score)  

- Implemented **Aspect-Based Sentiment Analysis (ABSA)**:
  - Treated each company/technology mention as an aspect  
  - Extracted context windows around mentions  
  - Predicted sentiment per aspect  
  - Aggregated results by company, technology, article, and topic  

---

### Key Findings

- AI news coverage is predominantly **neutral**, indicating informational reporting rather than strong opinion  

- **Industry differences are significant**:
  - Positive sentiment: enterprise software, business operations  
  - Negative/mixed sentiment: media, publishing, entertainment  

- **Market-sensitive sectors**:
  - Cryptocurrency shows high sentiment volatility  
  - Public AI companies trend more positively over time  

- **Big Tech dominance**:
  - Companies like Google, Microsoft, Amazon, Apple, and Nvidia dominate AI discourse across industries  

- AI adoption is most successful when it **enhances existing workflows**, and more controversial when it introduces **regulatory or creative disruption**  

---

### Project Workflow

Run the notebooks in the following order:

`cleaning.ipynb`  
→ `topic_detection_*.ipynb`  
→ `ner.ipynb`  
→ `ner_analysis.ipynb`  
→ `train_sentiment.ipynb`  
→ `absa.ipynb`

Each step builds on the previous one and generates intermediate outputs used downstream.

---

### Important Notes

- The trained sentiment model and `.parquet` output files are **not included** due to GitHub file size limits  

- If you run the notebooks locally in the correct order, all outputs (including models and parquet files) will be **recreated automatically**

---

### Project Deliverables

- Jupyter Notebooks  
  → Full pipeline including preprocessing, topic modeling, NER, sentiment training, and ABSA  

- Presentation (`NLP Final Slides.pptx`)  
  → Summary of methodology, results, and insights used for final class presentation  

---

## Skills & Concepts Demonstrated

- NLP pipelines and text preprocessing  
- Topic modeling: **LDA, NMF, BERTopic**  
- Named Entity Recognition (spaCy, rule-based matching)  
- Transformer models (DistilRoBERTa)  
- Aspect-Based Sentiment Analysis (ABSA)  
- Large-scale text data processing (~200K documents)  
- Unsupervised + supervised learning integration  
- Model evaluation (precision, recall, F1 score)  
- Working with PyTorch and Hugging Face ecosystem  
- Communicating insights through structured analysis and presentations  

---
