# Sentiment Analysis on Amazon Product Reviews

This repository contains the implementation of **Problem 2: Sentiment Analysis of Reviews**, developed as part of the **Quera AI Bootcamp** group project.  
The goal of this project is to analyze Amazon electronic product reviews and build a model capable of predicting the sentiment (rating 1–5) of each review using Natural Language Processing (NLP) and Machine Learning techniques.

---

## Table of Contents

-   [Overview](#-overview)
-   [Dataset Description](#-dataset-description)
-   [Project Structure](#-project-structure)
-   [Tasks Overview](#-tasks-overview)
    -   [Part 1 — Exploratory Data Analysis (EDA)](#part-1--exploratory-data-analysis-eda)
    -   [Part 2 — Aspect-Based Satisfaction Analysis](#part-2--aspect-based-satisfaction-analysis)
    -   [Part 3 — Sentiment Classification Model](#part-3--sentiment-classification-model)
-   [Model Details](#-model-details)
-   [Repository Branches](#-repository-branches)
-   [Results and Reports](#-results-and-reports)
-   [Contributors](#-contributors)
-   [Acknowledgments](#-acknowledgments)
-   [License](#-license)

---

## Overview

Sentiment Analysis is a subfield of Natural Language Processing (NLP) focused on identifying and extracting subjective information from text — such as opinions, emotions, or attitudes.  
In this project, we analyzed **Amazon product reviews** to uncover patterns in customer satisfaction and to train a model that predicts review ratings from 1 to 5 based on text content.

---

## Dataset Description

The dataset includes reviews of electronic products from Amazon.  
The data was accessed directly from Google Drive within the notebooks (not stored in this repository).  
Below are the main columns of the dataset used:

| Column           | Description                                  |
| :--------------- | :------------------------------------------- |
| `overall`        | Product rating (1–5)                         |
| `vote`           | Number of helpful votes                      |
| `verified`       | Whether the review is verified               |
| `reviewTime`     | Date of the review                           |
| `reviewerID`     | Unique user ID                               |
| `asin`           | Product ID                                   |
| `style`          | Product attributes such as color, size, etc. |
| `reviewerName`   | Name of reviewer                             |
| `reviewText`     | Full review text                             |
| `summary`        | Short summary of the review                  |
| `unixReviewTime` | Review timestamp in UNIX format              |

---

##  Project Structure

```
📁 sentiment-analysis-project/
│
├── 📄 README.md
├── 📄 QBC_Project2_Group1.pdf          # Report including outputs and analyses from all parts
│
├── 📂 eda/                             # Part 1 - Exploratory Data Analysis
│   └── eda.ipynb
│
├── 📂 feature-warranty-sentiment-analysis/   # Part 2 - Warranty/Aspect-based analysis
│   └── warranty_sentiment_analysis_using_sentence_bert.ipynb
│
└── 📂 sentiment-analysis-model/        # Part 3 - Sentiment classification model
    └── sentiment-analysis-deberta.ipynb
    └── sentiment-analysis-distilbert.ipynb
```

> Note: The dataset is **not included** in this repository and is loaded directly from Google Drive in each notebook.

---

## Tasks Overview

### Part 1 — Exploratory Data Analysis (EDA)

In this section, we explored the dataset to understand its structure and statistical patterns:

-   Visualized rating distribution (`overall`)
-   Generated **Word Clouds** for positive, neutral, and negative reviews
-   Found **Top 10 reviewers** based on total helpful votes
-   Analyzed **review text lengths** to detect outliers
-   Identified **top products and brands** based on number of 5-star reviews and average scores

---

### Part 2 — Aspect-Based Satisfaction Analysis

This section estimates **customer satisfaction with product warranty**.  
Steps included:

-   Searching for reviews containing terms like `"warranty"` or `"guarantee"`
-   Using **word embeddings** to detect semantically similar words
-   Accounting for **typos and variations**
-   Calculating **average sentiment per product** for warranty-related reviews

> The approach leverages vector similarity to improve recall beyond simple keyword search.

---

### Part 3 — Sentiment Classification Model

In this section, we fine-tuned transformer-based models to predict review sentiment scores (1–5) from text.

#### Models Used

-   **DeBERTa** (Microsoft)
-   **DistilBERT** (Hugging Face)

#### Steps

1. Text preprocessing and tokenization
2. Splitting data into training and validation sets
3. Fine-tuning transformer models on review text
4. Evaluating models using **F1-score (micro average)**
5. Generating predictions for the test dataset

---

##  Model Details

| Model      | Base Architecture          | Fine-Tuning Strategy                               | Evaluation Metric |
| :--------- | :------------------------- | :------------------------------------------------- | :---------------- |
| DeBERTa    | Transformer                | Fine-tuned on review text with classification head | F1 (micro)        |
| DistilBERT | Transformer (compact BERT) | Fine-tuned with reduced dataset for efficiency     | F1 (micro)        |

---

## Repository Branches

This project includes the following branches, corresponding to each part of the assignment:

| Branch                                | Description                                |
| :------------------------------------ | :----------------------------------------- |
| `eda`                                 | Exploratory Data Analysis                  |
| `feature/warranty-sentiment-analysis` | Aspect-based (warranty) sentiment analysis |
| `sentiment-analysis-model`            | Sentiment classification model             |
| `main`                                | Final merged branch containing all parts   |

---

## Results and Reports

All outputs, figures, and findings are compiled in:

📄 **`QBC_Project2_Group1.pdf`**

> Includes complete results and visualizations from all three parts of the project.

---

## Contributors

This project was developed collaboratively by a team of three participants from the **Quera AI Bootcamp**:

| Name                | GitHub                              |
| :------------------ | :---------------------------------- |
| **Bamdad Agin**     | [https://github.com/bamdadagin](#)  |
| **Elham Saberi**    | [https://github.com/elli-saberi](#) |
| **Reza Khoshgavar** | [https://github.com/RezaKhRKH](#)   |

---

##  Acknowledgments

This project was developed as part of the **Quera Artificial Intelligence Bootcamp**, aiming to strengthen practical understanding of NLP, data preprocessing, and transformer-based modeling.  
Special thanks to the mentors and the Quera AI team for their support and feedback.

---



