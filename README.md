# Drug-Review-Sentiment-Analysis-RoBERTa-vs-Claude-LLM
An end-to-end Natural Language Processing project that analyzes patient drug reviews using a transformer-based sentiment model (RoBERTa) and benchmarks it against Anthropic's Claude LLM — combined with dimensionality reduction and unsupervised clustering to uncover patterns in patient experiences.

## Project Objective

To analyze patient drug reviews and identify sentiment patterns and review groupings using a combination of classical NLP, transformer models, and modern Large Language Models (LLMs). Since the dataset lacks a sentiment label, sentiment is inferred — first using RoBERTa, then independently using Claude, with the two methods compared side-by-side.

## Dataset
Drug Review Dataset (Kaggle) — 161,000+ patient reviews across hundreds of medical conditions.

Tech Stack
Python 3.10+
pandas, numpy — Data manipulation
matplotlib, seaborn — Visualization
scikit-learn — TF-IDF vectorization, TruncatedSVD, K-Means
transformers (Hugging Face) — RoBERTa sentiment model (cardiffnlp/twitter-roberta-base-sentiment)
anthropic — Claude LLM API for prompt-based sentiment classification


## Project Workflow
Initial Look — Dataset overview, shape, info, missing values
Exploratory Data Analysis (EDA) — Rating distributions, top conditions, top drugs, review length analysis
Data Cleaning — Handling missing values, duplicates, type conversions
Data Preprocessing — Text normalization, lowercasing, punctuation removal
Sentiment Analysis with RoBERTa — Classifying reviews as positive, neutral, or negative
Dimensionality Reduction — TF-IDF features reduced via TruncatedSVD to 2D for visualization
Elbow Method — Selecting the optimal number of clusters
K-Means Clustering — Grouping reviews by similarity
Cluster Insights — Interpreting clusters via sentiment distribution, top conditions, top drugs, and sample reviews
LLM Comparison (Claude) — Re-classifying the same reviews with Claude and comparing agreement with RoBERTa

## Key Highlights
Two sentiment approaches benchmarked side-by-side:

RoBERTa — A pre-trained transformer model fine-tuned on Twitter data
Claude (claude-haiku-4-5) — Prompt-engineered LLM classification

Unsupervised review segmentation using TF-IDF + TruncatedSVD + K-Means
Insight-driven interpretation of clusters using condition, drug, and review patterns
Honest reporting of limitations — sample size, domain mismatch, computational constraints

## Sample Findings
Birth Control is the most-reviewed condition, followed by Depression, Pain, Anxiety, and Acne
Ratings are bimodal — many reviews are strongly positive (10) or strongly negative (1)
RoBERTa and Claude often agree on clearly positive or negative reviews; disagreements emerge on reviews with mixed sentiment or nuanced language

## Getting Started
Prerequisites
Python 3.10 or higher
Anthropic API key (for the LLM section) — get one at console.anthropic.com
Kaggle account to download the dataset

## Environment
The notebook was originally developed in Google Colab and uses Google Drive for dataset storage. To run locally:
Download the dataset from Kaggle
Update the file paths in the notebook to point to your local copy
Set your Anthropic API key as an environment variable (do NOT hardcode it)

## Limitations
Sample-based RoBERTa & Claude analysis — A random sample was used for the transformer/LLM sections due to compute constraints. Results represent patterns within the sample.
Domain mismatch — The RoBERTa model used was trained on social media text, not medical reviews. Sentiment predictions should be treated as general estimates.
Clustering is exploratory — Cluster labels reflect data patterns, not medical categories.

## Future Work
Scale RoBERTa and Claude sentiment classification to the full dataset
Fine-tune a transformer on medical-domain text for better accuracy
Add inter-rater agreement metrics (e.g., Cohen's Kappa) for RoBERTa vs Claude
Deploy as a Streamlit app for interactive review classification

## Author
AJ 
Licensed Pharmacist • Junior Officer • Python + AI Bootcamp Graduate
This project was completed as part of the UPLIFT Code Camp Python + AI Bootcamp (Feb–Jul 2026).

## License
This project is open for educational and portfolio purposes. The dataset is provided by Kaggle under its respective terms.

## Acknowledgements
Kaggle / Jessica Li — for the Drug Review Dataset

CardiffNLP — for the RoBERTa sentiment model on Hugging Face

Anthropic — for the Claude API

UPLIFT Code Camp — for the structured bootcamp and project guidance
