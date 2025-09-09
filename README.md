📊 Amazon Reviews Sentiment Analysis (NLP Project)

📌 Problem Statement
Customer reviews play a crucial role in shaping brand reputation and sales. Manually analyzing thousands of reviews is time-consuming and inconsistent.
This project automates sentiment classification of Amazon reviews, helping businesses quickly identify negative feedback and improve customer satisfaction.

📂 Dataset

Source: Amazon Fine Food Reviews (Kaggle)

Rows: ~568,000 reviews

Target Variable: Sentiment (Positive / Negative)

Features Used:

Score (1–5 stars, mapped to sentiment: 1–2 = negative, 3 = neutral (dropped), 4–5 = positive)

Text (review content)

🛠 Methodology
Data Cleaning

Dropped neutral reviews for binary classification (positive vs negative).

Removed missing/blank values.

Cleaned text: lowercased, removed HTML, URLs, punctuation, and extra spaces.

Feature Engineering

TF-IDF vectorization (unigrams + bigrams, min_df=5, max_df=0.9, sublinear TF, stopwords removed).

Modeling

Baseline: Dummy Classifier (random guess based on class frequency).

Multinomial Naive Bayes: Classic text classifier.

Logistic Regression: Linear model with class balancing.

Evaluation

Confusion Matrix

Accuracy, Precision, Recall, F1-score

Top positive/negative feature words

📊 Results
Performance Table

Confusion Matrix (Logistic Regression – Test Set)

Model Insights

Logistic Regression achieved 95% accuracy with 91% recall for negatives, making it the best model.

Naive Bayes reached 93% accuracy but weaker negative recall (59%).

Baseline only managed 74% accuracy and failed on negatives.

Top Features

Positive words: delicious, excellent, perfect, tasty, amazing

Negative words: terrible, disappointed, waste, bland, awful

(Feature importance bar chart can be added here)

📌 Business Value

Flags negative customer reviews early → businesses can act before churn or reputational damage.

Provides interpretable insights into what words drive sentiment.

Helps product and customer support teams focus on real pain points.

🚀 Future Work

Extend to multi-class classification (positive / neutral / negative).

Experiment with Linear SVM and transformer models (BERT).

Build a Streamlit app for real-time sentiment prediction.
