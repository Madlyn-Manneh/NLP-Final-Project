# Zero-Shot and Few-Shot Cross-Lingual Sentiment Analysis from English to Krio

## Overview

This project explores cross-lingual sentiment analysis for Krio, a low-resource English-lexified creole spoken in Sierra Leone.

The study compares multilingual transformer models:

-mBERT (`bert-base-multilingual-cased`)
-XLM-R (`xlm-roberta-base`)

for ternary sentiment classification:

-Negative
-Neutral
-Positive

The project investigates:

-Zero-shot learning
-Few-shot learning (10-shot and 50-shot)
-Balanced few-shot training
-Cross-lingual transfer from English to Krio

---

## Key Features

-Few-shot learning for low-resource NLP
-Cross-lingual sentiment transfer
-mBERT vs XLM-R comparison
-Balanced sampling experiments
-TF-IDF + Logistic Regression baseline
-Error analysis and confusion matrices

---

## Dataset

### English Dataset

-dair-ai/emotion` from Hugging Face
-Mapped into:

  -Negative
  -Neutral
  -Positive

### Krio Dataset
-200 manually annotated Krio sentences
-Sampled from `Jaward/Krio-Corpus`
-Used for few-shot training and evaluation

---

## Models Used

### Baseline

-TF-IDF Vectorizer
-Logistic Regression

### Transformer Models

-mBERT (`bert-base-multilingual-cased`)
-XLM-R (`xlm-roberta-base`)

---

## Experimental Setup

The project evaluates:

| Setting          | Description                     |
| ---------------- | ------------------------------- |
| Zero-shot        | Train on English only           |
| 10-shot          | Fine-tune with 10 Krio examples |
| 50-shot          | Fine-tune with 50 Krio examples |
| Balanced 50-shot | Equal class sampling            |

---

## Results

| Experiment       | mBERT         | XLM-R         |
| ---------------- | ------------- | ------------- |
| Zero-shot        | 0.200 / 0.168 | 0.180 / 0.169 |
| 10-shot          | 0.573 / 0.263 | 0.227 / 0.123 |
| 50-shot          | 0.580 / 0.245 | 0.580 / 0.245 |
| Balanced 50-shot | 0.453 / 0.324 | —             |

Format:

* Accuracy / Macro F1

### Key Findings

-Few-shot learning significantly improved performance.
-mBERT slightly outperformed XLM-R in this low-resource setting.
-Balanced sampling improved Macro F1 and reduced Neutral-class bias.

---

## Technologies

-Python
-PyTorch
-Hugging Face Transformers
-scikit-learn
-pandas
-numpy
-matplotlib
-seaborn

---

## Repository Structure

```text
.
├── NLP_Final_Project.ipynb
├── Balanced__Few_shot.ipynb
├── krio_annotation.csv
└── README.md
```

---

## How to Run

### 1. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn transformers datasets torch evaluate
```

### 2. Run the Notebooks

Open Jupyter Notebook or Google Colab and run:

```text
NLP_Final_Project.ipynb
Balanced__Few_shot.ipynb

---

### Research Contribution

This project contributes:

-One of the first annotated Krio sentiment datasets
-A comparative study of mBERT and XLM-R for Krio NLP
-Insights into few-shot learning for low-resource creole languages

---

## Author

Madlyn Manneh

MSc Data Science – NLP Final Project
