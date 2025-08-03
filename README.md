# Email Spam Detection using Naive Bayes
---
## Table of Contents
* [Project Overview](#project-overview)
* [Methodology](#methodology)
    * [Data Loading](#data-loading)
    * [Data Cleaning](#data-cleaning)
    * [Class Distribution](#class-distribution)
    * [Word Clouds](#word-clouds)
    * [Vectorization](#vectorization)
    * [Model Training](#model-training)
    * [Model Evaluation](#model-evaluation)
* [Results](#results)
* [Conclusion](#conclusion)

---
## Project Overview
This project aims to build a classification model that can accurately detect whether an email is spam or ham (not spam) using Naive Bayes algorithms. The model is trained on a dataset of 5169 emails, with 87% being ham and 13% being spam.

---
## Methodology
### Data Loading
The dataset is loaded into a Pandas DataFrame.

### Data Cleaning
The data is cleaned by removing duplicates, converting text to lowercase, and removing punctuation.

### Class Distribution
The class distribution of the dataset is visualized and the class ratio is calculated.

### Word Clouds
Word clouds are created for spam and ham messages to visualize the most common words.

### Vectorization
The text data is vectorized using TF-IDF to extract features.

### Model Training
A Multinomial Naive Bayes model is trained on the vectorized data.

### Model Evaluation
The model is evaluated using classification report and confusion matrix.

---
## Results
The results of the project are:
* **Precision**: The model achieves 100% precision for spam emails.
* **Recall**: The model achieves 71% recall for spam emails.
* **Accuracy**: The model achieves 96% accuracy on the test set.

---
## Conclusion
The Multinomial Naive Bayes model performs strongly on the dataset, achieving high precision and accuracy. This makes it a reliable choice for detecting spam emails, especially in scenarios where avoiding false positives is more critical than catching every spam message.
