# Arabic Aspect-Based Sentiment Analysis (ABSA)

Reproduction and critical analysis of the research paper **"AraABSAMD: A novel Arabic dataset for aspect-based sentiment analysis in the Moroccan education domain"** (Lachhab & Ziyati, 2026).

## Project Overview

This project explores Arabic Aspect-Based Sentiment Analysis (ABSA) through the reproduction and critical analysis of the AraABSAMD research paper.

The work focuses on two main tasks:

- **Aspect Category Detection (ACD):** identifying the aspect category associated with an aspect.
- **Aspect Category Polarity (ACP):** determining the sentiment polarity associated with an aspect.

The experiments compare a traditional machine learning baseline with several Arabic pretrained language models.

## Dataset

The AraABSAMD dataset concerns the Moroccan education domain and contains:

- 1,360 annotated sentences.
- 4,623 annotated aspect terms.

**Important limitation:** The original tweet texts are not distributed with the dataset. The reproduction therefore uses concatenated aspect terms rather than the original full tweets. Consequently, the experimental results should not be considered directly comparable to the original paper results.

## Methodology

The project follows these main steps:

1. XML dataset inspection and exploration.
2. Data preprocessing.
3. Implementation of a TF-IDF + SVM baseline.
4. Fine-tuning and evaluation of pretrained Arabic language models.
5. Comparison of the models using Macro F1-score.
6. Critical analysis of the experimental results and limitations.

## Models

The following approaches were evaluated:

| Model | Description |
|---|---|
| TF-IDF + SVM | Traditional machine learning baseline |
| AraBERTv2 | Arabic pretrained language model |
| ARBERT | Arabic pretrained language model |
| CAMeLBERT-msa | Arabic pretrained language model for Modern Standard Arabic |

## Experimental Results

The following table presents the obtained Macro F1-scores.

| Model | ACD | ACP |
|---|---:|---:|
| TF-IDF + SVM | 0.58 | 0.39 |
| AraBERTv2 | 0.63 | 0.40 |
| ARBERT | **0.71** | **0.51** |
| CAMeLBERT-msa | 0.69 | 0.45 |

ARBERT achieved the best results among the evaluated models for both ACD and ACP.

## Critical Analysis

The experiments highlight the benefits of pretrained Arabic language models compared with a traditional TF-IDF + SVM baseline.

However, the absence of the original tweet texts represents an important limitation. Using concatenated aspect terms changes the input representation and may affect the models' ability to capture contextual information.

The results should therefore be interpreted within the specific reproduction setting rather than as a direct replication of the original experimental conditions.

## Repository Structure

```text
arabic-absa-nlp-reproduction/
│
├── notebooks/
│   └── Data_NLP.ipynb
│
├── reports/
│   ├── presentation.pdf
│   └── rapport-analyse-critique.pdf
│
├── README.md
├── requirements.txt
└── .gitignore
Technologies
- Python
- Pandas
- NumPy
- Scikit-learn
- PyTorch
- Hugging Face Transformers
- AraBERTv2
- ARBERT
- CAMeLBERT-msa
- Jupyter Notebook
Repository Contents
- notebooks/Data_NLP.ipynb: data exploration, preprocessing, model implementation and evaluation.
- reports/presentation.pdf: project presentation.
- reports/rapport-analyse-critique.pdf: detailed report and critical analysis.
- requirements.txt: Python dependencies.
Reference
Lachhab, A., & Ziyati, A. (2026). AraABSAMD: A novel Arabic dataset for aspect-based sentiment analysis in the Moroccan education domain. Array.

DOI: https://doi.org/10.1016/j.array.2026.100782
Author
Sarra Bouguerra
Data Science Engineering Student
Université Sesame, Tunisia

