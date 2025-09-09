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
Confusion Matrix (Logistic Regression – Test Set)

Model Performance
Model	Accuracy	Recall (Negative)	F1 (Negative)
Baseline (dummy)	74%	0.15	0.15
Naive Bayes	93%	0.59	0.73
Logistic Regression ⭐	95%	0.91	0.84

Logistic Regression significantly outperformed Naive Bayes and baseline.

Strong recall for negatives (91%) → critical for detecting unhappy customers.

![image alt](https://github.com/LakshayJakhar/amazon-reviews-sentiment-analysis/blob/7f2d472e8193ad5688ba15dd743f75ec13da1e92/images/Table.png)


Top Features

Positive words: delicious, excellent, perfect, tasty, amazing

Negative words: terrible, disappointed, waste, bland, awful

(Add feature importance bar chart here)

📌 Business Value

Flags negative customer reviews early → businesses can act before churn or reputational damage.

Provides interpretable insights into what words drive sentiment.

Helps product and customer support teams focus on real pain points.

🚀 Future Work

Extend to multi-class classification (positive / neutral / negative).

Experiment with Linear SVM and transformer models (BERT).

Build a Streamlit app for real-time sentiment prediction.



