
# Text-Based Emotion Detection in Banglish, Bangla, and English

This project investigates text-based emotion classification in **Banglish (Romanized Bangla), Bangla, and English**, with particular attention to the challenges of developing labeled resources for low-resource languages. It includes the construction and annotation of a Banglish emotion dataset and experiments with traditional machine learning, deep neural networks, and BERT-based models.

**[Read the research report (PDF)](docs/Text_Based_Emotion_Detection_Report.pdf)**

## Research Overview

Emotion classification in Banglish is challenging because informal online writing often contains inconsistent transliteration, spelling variations, and limited labeled training data.

The project explored two research questions:

1. How can a labeled Banglish dataset be collected, cleaned, annotated, and expanded for six-class emotion classification?
2. How do different machine-learning, deep-learning, and transformer-based approaches perform on Banglish, Bangla, and English text datasets?

The Banglish and Bangla experiments consider six emotions: **anger, disgust, fear, happiness/joy, sadness, and surprise**. The English experiments use the labels provided by their respective benchmark datasets.

## Dataset Development

The team collected approximately **3,500** candidate Banglish texts from social media and retained **3,044** after cleaning.

Four student annotators assigned emotion labels. Disagreements were resolved through majority voting and discussion, with ambiguous examples removed. The report gives an inter-annotator agreement score of **0.89 (reported as Cohen's kappa)**.

To increase the amount of training data, the project used a transliteration/translation-assisted Easy Data Augmentation (EDA) pipeline.

After augmentation and further manual cleaning, the Banglish dataset contained **7,611 samples**.

### Datasets Used

| Language | Dataset | Task |
| --- | --- | --- |
| Banglish | Team-collected, annotated, and augmented corpus | Six-class emotion classification |
| Bangla | BEmoD | Six-class emotion classification |
| English | ISEAR | Emotion classification |
| English | IMDB and SST-2 | Sentiment classification |

**Data availability:** A `BEmoD dataset.zip` archive is present in this repository. The team-created Banglish corpus is described in the report but is not included in the current repository.

## Methodology

Multiple approaches were investigated to evaluate emotion classification performance across different languages.

### Feature Extraction

- TF-IDF
- Word2Vec
- GloVe
- FastText

### Traditional Machine Learning

- Random Forest
- Support Vector Machine (SVM)
- Logistic Regression
- Decision Tree
- Naive Bayes
- XGBoost
- Gradient-descent-based classification

### Deep Learning

- Convolutional Neural Network (CNN)
- CNN + Bidirectional LSTM (BiLSTM)
- CNN + Attention + BiLSTM
- CNN + Attention + LSTM

Different word embeddings were evaluated alongside these architectures.

### Transformer-Based Models

- BERT Base
- Multilingual BERT
- Bangla BERT

### Evaluation

Performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices

The experiments also compared classification performance before and after Banglish data augmentation.

## Experimental Results

### Selected Results

| Dataset | Model / Approach | Reported Accuracy |
| --- | --- | ---: |
| Banglish (augmented) | Random Forest + TF-IDF | **67.95%** |
| Banglish (augmented) | CNN + BiLSTM + FastText | **67.54%** |
| Bangla (BEmoD) | Bangla BERT | **62.19%** |
| English (IMDB) | BERT-based experiment | **94.98%** |
| English (SST-2) | BERT-based experiment | **94.89%** |

These results are taken from the original 2022 research report. They have not been independently rerun or reverified.

Results across different datasets and classification tasks are not directly comparable. Some reported figures and model rankings differ between sections of the original report.

### Key Findings

- Data augmentation and manual cleaning improved the performance of several Banglish classification models.
- Random Forest with TF-IDF achieved the highest reported accuracy among traditional ML approaches on the augmented Banglish dataset.
- CNN + BiLSTM architectures produced competitive results for Banglish emotion classification.
- Bangla BERT achieved the highest reported accuracy on the BEmoD dataset.
- Data quality, transliteration inconsistencies, and limited labeled resources remained important challenges.

## Repository Structure

The repository contains:

- `*.ipynb` — Jupyter notebooks containing experiments with machine learning, deep learning, word embeddings, and BERT-based models.
- `BEmoD dataset.zip` — available Bangla emotion dataset archive.
- `docs/Text_Based_Emotion_Detection_Report.pdf` — research report containing the methodology, experimental analysis, results, conclusions, and references.

### Running the Experiments

The notebooks are research artifacts rather than a packaged application.

Individual experiments may require:

- Python and Jupyter Notebook or Google Colab
- TensorFlow / Keras
- scikit-learn
- Hugging Face Transformers
- NLTK
- Pretrained word embeddings
- Associated datasets

Some notebooks may depend on external datasets, older library versions, or environment-specific paths. A verified end-to-end reproduction environment is not currently provided.

## Limitations

The research identified several challenges:

- Limited availability of labeled Banglish datasets
- Inconsistent transliteration and spelling
- Ambiguous emotional expressions
- Errors introduced during translation and augmentation
- Differences in performance across emotion categories
- Computational requirements of transformer-based models

Further research could investigate larger datasets, improved annotation procedures, and language-specific pretrained models for Banglish.

## Research Report

The complete research report includes:

- Introduction and related work
- Dataset development and preprocessing
- Machine learning and deep learning approaches
- Transformer-based experiments
- Experimental results and error analysis
- Conclusion and references

**[View Research Report (PDF)](docs/Text_Based_Emotion_Detection_Report.pdf)**
