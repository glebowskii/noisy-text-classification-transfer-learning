# Noisy Text Classification with Transfer Learning

This project demonstrates a full NLP pipeline including data collection, preprocessing, and model training using transfer learning with pretrained TinyBERT embeddings.

## Overview

The goal of this project is to train a model to distinguish between two types of text:
- encyclopedic text (Wikipedia)
- informal / noisy text (Telegram channels)

This setup allows the model to learn differences between structured, formal language and unstructured, user-generated content.

The task is formulated as a supervised binary classification problem.

## Approach

The project follows a full machine learning pipeline:

1. **Data collection**
   - Wikipedia articles are parsed and used as examples of formal text
   - Telegram messages are collected as examples of informal/noisy text

2. **Preprocessing**
   - Text cleaning and normalization
   - Dataset construction for both domains

3. **Dataset construction**
   - Two datasets are built separately and then merged into a single labeled dataset

4. **Modeling**
   - Text embeddings are obtained using a pretrained Russian TinyBERT model
   - A classifier is trained on top of these embeddings
   - The setup follows a transfer learning approach, where pretrained language representations are reused for downstream classification

5. **Training**
   - The model is trained using PyTorch
   - Standard training loop with batching, loss computation, and optimization

## Model

The model uses:
- pretrained TinyBERT embeddings (transfer learning)
- a simple feedforward neural network classifier

This approach allows leveraging pretrained language representations while keeping the classification head lightweight.

## Repository structure

- `wiki_parsing.ipynb` — Wikipedia data collection  
- `wiki_dataset.ipynb` — preprocessing and dataset creation (Wikipedia)  
- `telegram_text_processing.ipynb` — preprocessing of Telegram data  
- `telegram_text_dataset.ipynb` — dataset creation (Telegram)  
- `join_datasets.ipynb` — merging datasets  
- `transfer_learning.ipynb` — model training and evaluation  

## Notes

This project was developed during my undergraduate studies.  
More recent work on language models and model controllability was conducted during a research internship at LIG (GETALP) and is not publicly available.

## Tech Stack

- Python  
- PyTorch  
- Hugging Face Transformers  
- Pandas, NumPy  