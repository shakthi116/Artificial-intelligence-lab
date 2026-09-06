# Sentiment Analysis using NLP

from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB

# Training data
texts = [
    "I love this movie",
    "This movie is excellent",
    "The product is very good",
    "I am happy with the service",
    "I hate this movie",
    "This movie is terrible",
    "The product is very bad",
    "I am unhappy with the service"
]

# Labels
labels = [
    "Positive",
    "Positive",
    "Positive",
    "Positive",
    "Negative",
    "Negative",
    "Negative",
    "Negative"
]

# Convert text into numerical features
vectorizer = CountVectorizer()
X = vectorizer.fit_transform(texts)

# Train Naive Bayes classifier
model = MultinomialNB()
model.fit(X, labels)

# Test sentences
test_texts = [
    "This movie is good",
    "The product is terrible"
]

# Convert test text
X_test = vectorizer.transform(test_texts)

# Predict sentiment
predictions = model.predict(X_test)

# Display results
for text, sentiment in zip(test_texts, predictions):
    print("Text:", text)
    print("Sentiment:", sentiment)
    print()
