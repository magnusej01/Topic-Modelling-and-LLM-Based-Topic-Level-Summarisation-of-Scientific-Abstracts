# Topic-Modelling-and-LLM-Based-Topic-Level-Summarisation-of-Scientific-Abstracts

## Overview

This project combines BERTopic with large language models to analyse and summarise a collection of 100 IEEE research paper abstracts related to sentiment analysis in news. The pipeline identifies latent topics using semantic embeddings and clustering, then generates topic level summaries using BART, Llama 3, and Mistral. The generated summaries are evaluated using ROUGE metrics and an LLM based judge approach inspired by the LimTopic framework.

This project was completed as part of the course DSP5200: Data Analytics with Generative AI and Large Language Models.

---

## Objectives

1. Collect and clean IEEE research abstracts  
2. Apply BERTopic to discover coherent topic clusters  
3. Generate topic level summaries using multiple language models  
4. Compare summarisation quality using ROUGE 1, ROUGE 2, and ROUGE L  
5. Evaluate readability and coherence using LLM based judges  
6. Reflect on strengths, limitations, and model behaviour  

---

## Methodology

### Dataset

100 IEEE Xplore abstracts  
Filtered by keywords related to news and sentiment analysis  
Collected across the years 2021 to 2025  

Metadata was exported in BibTeX format and converted to a structured dataset.

---

### Topic Modelling with BERTopic

BERTopic was used together with:

Sentence BERT embeddings  
UMAP for dimensionality reduction  
HDBSCAN for density based clustering  
c TF IDF for topic representation  

The model produced **three coherent topics**, each representing distinct research themes such as:

• news and social media analysis  
• sentiment analysis methodology  
• financial sentiment and market analysis  

Topic coherence was computed to confirm meaningful clustering.

---

### Summarisation Models

The following models were applied to generate topic level summaries:

Facebook BART Large CNN  
Meta Llama 3 8B Instruct  
Mistral 7B Instruct  

Because of model context limits, a controlled summarisation strategy was designed that prevents truncation and preserves information across abstracts. All models received the same topic level inputs and a shared summarisation prompt style.

---

### Evaluation

Two complementary evaluation strategies were used:

#### ROUGE Scores
ROUGE 1  
ROUGE 2  
ROUGE L  

Measured against human written topic summaries.

#### LLM as a Judge

GPT 5.1 and Claude Sonnet 4.5 were used to score:

• coherence  
• readability  
• fluency  
• grammaticality  
• relevance  

Scores were averaged across topics to ensure fair comparison.

---

## Key Findings

• BERTopic produced clear and interpretable topics  
• Llama 3 and Mistral outperformed BART across most evaluation metrics  
• Mistral tended to retain more word and phrase level content  
• Llama 3 aligned best with human written structural flow  
• BART struggled with longer multi document input  
• LLM judges broadly agreed with ROUGE score trends  

The study shows that combining topic modelling with LLM summarisation is a practical way to analyse research literature at scale.

---

## Technology and Tools

### NLP and Topic Modelling
Python  
BERTopic  
Sentence Transformers (all mpnet base v2)  
spaCy  
Gensim CoherenceModel  

### Summarisation and LLMs
Hugging Face Transformers  
BART Large CNN  
Llama 3 8B Instruct  
Mistral 7B Instruct  

### Data and Utilities
Pandas  
NumPy  

### Visualisation
Matplotlib  
Seaborn  

---

## Learning Outcomes

Through this project I strengthened my skills in:

Designing NLP pipelines  
Working with semantic text embeddings  
Applying neural topic modelling  
Designing controlled LLM summarisation workflows  
Evaluating multi document summarisation  
Using LLMs as qualitative judges  
Handling token limits and chunking strategies  

---
