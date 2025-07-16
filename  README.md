# 🔮 Article Sentiment Predictor – Like or Dislike?

Predict whether a web article will be *Liked* 👍 or *Disliked* 👎 based on the **vocabulary choice of the writer** using a **Naïve Bayes classifier**.

This project demonstrates a complete ML pipeline for natural language classification using real news data. It focuses on how the vocabulary in headlines and descriptions influences reader sentiment.

---

## 📌 Project Highlights

- ✅ **Binary Sentiment Classification**: Like (👍) vs. Dislike (👎)
- 🧠 **Model Used**: Custom-built Naïve Bayes classifier
- 📊 **Dataset**: Cleaned and sampled from real-world news categories
- 🧹 **Preprocessing**: Custom stopword removal + tokenization
- 💾 **Model Persistence**: Save and load with compressed `.pkl.gz` format
- 📈 **Metrics Evaluated**: Accuracy, Precision, Recall, F1 Score
- 🧪 **Evaluation**: Confusion Matrix + Top predictive words
- 🔄 **Reusable**: Easily plug in any text to predict like/dislike

---

## 🗂️ Folder Structure

  ├── naive_bayes_model.pkl.gz    # Trained and compressed model
  ├── News_Category_Dataset_v3.json  # Dataset used
  ├── notebook.ipynb              # Full training & evaluation pipeline
  ├── README.md                   # This file
  └── .gitignore                  # Ignored files

---


## 🚀 How It Works

### 📥 1. Load & Sample Dataset

We filter four key categories:
- 👍 **Like**: `WELLNESS`, `ENTERTAINMENT`
- 👎 **Dislike**: `CRIME`, `POLITICS`

Balanced sampling ensures equal representation.

### 🧼 2. Text Preprocessing

- Lowercasing
- Removal of punctuation and digits
- Elimination of ~300+ common stopwords and contractions
- Tokenization into clean vocabulary lists

### 🤖 3. Naïve Bayes Model

Custom implementation trained on top 5000 words (by frequency). Laplace smoothing is used for unseen word handling. Model is saved in compressed `.pkl.gz` format for efficiency.

### 🧪 4. Evaluation Output

Example evaluation metrics:
- **Accuracy**: 90.0%
- **Precision**: 88.2%
- **Recall**: 92.1%
- **F1 Score**: 90.1%

Sample confusion matrix:
                        Predicted Like   Predicted Dislike
          Actual Like           132                14
          Actual Dislike         18               136


### 💡 5. Predictions

```python
predict_sentiment("Celebrity wedding announcement") # 👍 Like
predict_sentiment("Crime rate increases in urban areas") # 👎 Dislike


🛠️ Requirements

To run the code locally:  pip install pandas numpy

Or launch the notebook in Google Colab for a hassle-free experience.


🔍 Example Predictions

Article Snippet                                    Prediction
“New yoga techniques help reduce stress”            👍 Like
“Political tensions rise in the Middle East”        👎 Dislike
“Celebrity wedding announcement”                    👍 Like
“Crime rate increases in urban areas”               👎 Dislike


📦 Reusability

You can easily load the saved model and use it for new predictions:

from model import load_model, preprocess_text, predict_sentiment

model = load_model()
text = "New AI tech improves daily life"
print(predict_sentiment(text, model))


🤝 Contributing

Have a better dataset, improvements to preprocessing, or a new model idea (like SVM or BERT)? Feel free to open a PR or issue!


📜 License

This project is open-source under the MIT License.


🙋‍♂️ Author

Made with ❤️ by Nishant Kaushik
