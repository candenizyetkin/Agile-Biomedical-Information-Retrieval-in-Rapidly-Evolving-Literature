# Agile-Information-Retrieval-Using-Few-Shot-and-Zero-Shot-Prompt-Engineering
This is the repository for CENG543 Term Project (25'-26') by Can Deniz Yetkin

This repository contains the work for the CENG543 final term research project. The project's objective is to investigate the effectiveness of general-purpose Large Language Models (LLMs) as an agile and cost-effective alternative for information retrieval in the rapidly evolving field of biomedical literature.

Traditional dense retrievers are powerful but static. In a field like biomedicine, where new research is published daily, keeping these models current requires continuous, costly retraining.

This project asks the following core research question:

Can a general-purpose Large Language Model (LLM), guided by careful prompt engineering (zero-shot & few-shot), match the ranking and retrieval accuracy of a specialized, trained DPR model on a domain-specific biomedical dataset like PubMedQA? 

This study aims to assess the potential of a more flexible, powerful, and "agile" alternative for domain-specific information retrieval.


# Biomedical Question Answering: Dense Retrieval vs Prompt-Based LLMs

This repository contains the experimental code and analysis for a comparative study on biomedical question answering using dense retrieval models and prompt-based large language models (LLMs). The study focuses on evaluating retrieval effectiveness, answer accuracy, and uncertainty handling on the PubMedQA dataset.

## Project Motivation

Biomedical literature is rapidly growing, making it increasingly difficult for clinicians and researchers to manually retrieve relevant evidence. Dense retrieval models have shown strong performance but require domain-specific training and continuous maintenance. In contrast, large language models offer flexible zero-shot and few-shot inference without retraining. This project investigates whether prompt-based LLMs can serve as a practical alternative to dense retrieval approaches, or whether retrieval-based grounding remains essential.

## Dataset

- **Dataset:** PubMedQA
- **Subset Used:** 1,000 question–abstract pairs
- **Question Labels:** yes / no / maybe
- Each question is derived from a specific PubMed abstract, which serves as the ground-truth relevant document for retrieval experiments.

## Experimental Structure

The project is organized into two main notebooks:

### Notebook 1 – Dense Retrieval Evaluation
This notebook focuses on retrieval-only experiments.

**Models evaluated:**
- SapBERT (biomedical synonym-aligned encoder)
- PubMedBERT (mean pooled embeddings)
- DPR Context Encoder (trained on Natural Questions)

**Evaluation Metrics:**
- Recall@5
- Recall@10

**Key Result:**
SapBERT achieves near-saturated retrieval performance, highlighting the importance of retrieval-specific fine-tuning and biomedical synonym alignment.

### Notebook 2 – Prompt-Based LLM Evaluation
This notebook evaluates zero-shot and few-shot inference using open-weight LLMs.

**Models evaluated:**
- Phi-3 Mini (3.8B parameters)
- MedAlpaca (7B parameters)

**Prompting Strategies:**
- Zero-shot
- Few-shot (limited examples)

**Evaluation Focus:**
- Answer accuracy (yes/no)
- Behavior on "maybe" labeled questions
- Bias and uncertainty handling

## Key Findings

- Dense retrieval performance is primarily driven by retrieval-oriented fine-tuning rather than model size alone.
- Prompt-based LLMs show limited improvement from few-shot prompting.
- All LLM configurations exhibit a strong affirmative bias, predicting "yes" for 100% of "maybe" questions.
- Dense retrieval remains essential for reliable biomedical question answering.

## Reproducibility Notes

- All experiments were run using HuggingFace Transformers and FAISS.
- No fine-tuning was performed on LLMs.
- Random seeds were fixed where applicable.

## Future Work

- Evaluation with larger (100B+) LLMs
- Retrieval-Augmented Generation (RAG)
- Improved uncertainty-aware prompting strategies

## Author

Can Deniz Yetkin  
İzmir Institute of Technology (IZTECH)

