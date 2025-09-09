Amazon Reviews Sentiment Analysis 📊

End-to-end NLP project using the Amazon Fine Food Reviews dataset (~568k rows).
Goal: classify reviews as positive or negative using TF-IDF + Machine Learning models.

📂 Dataset

Source: Amazon Fine Food Reviews on Kaggle

Fields used:

Score (1–5 stars) → mapped to sentiment:

1–2 = Negative

3 = Neutral (dropped for binary classification)

4–5 = Positive

Text (review content)

🔧 Process

Data Preparation

Dropped missing/blank reviews

Converted scores → sentiment labels

Removed neutral reviews for binary classification

Text Cleaning

Lowercased

Removed HTML tags, URLs, punctuation, and extra spaces

Feature Engineering

TF-IDF vectorization (unigrams + bigrams, min_df=5, max_df=0.9, sublinear TF, stopwords removed)

Modeling

Baseline: DummyClassifier (stratified random guessing)

Multinomial Naive Bayes

Logistic Regression (final best model)

Evaluation

Accuracy, Precision, Recall, F1-score

Confusion Matrix

Top features visualization (positive vs negative words)

📊 Results
Model	Accuracy	Recall (Negative)	F1 (Negative)
Baseline (dummy)	74%	0.15	0.15
Naive Bayes	93%	0.59	0.73
Logistic Regression ⭐	95%	0.91	0.84

Logistic Regression clearly outperformed Naive Bayes and baseline.

Strong recall for negatives (91%) → critical for catching unhappy customers.

📉 Visuals
Confusion Matrix (Logistic Regression – Test Set)

![image alt](https://github.com/LakshayJakhar/amazon-reviews-sentiment-analysis/blob/7f2d472e8193ad5688ba15dd743f75ec13da1e92/images/Table.png)

Top Features

Positive words → "delicious", "excellent", "perfect"
Negative words → "terrible", "disappointed", "waste"

💡 Business Value

This model can:

Flag negative customer feedback early (91% recall).

Help businesses monitor satisfaction and prevent churn.

Provide interpretable insights into what words drive sentiment.

🚀 Future Improvements

Add multi-class classification (positive, neutral, negative).

Try Linear SVM or transformer models (BERT).

Deploy a simple Streamlit app for real-time sentiment analysis.
