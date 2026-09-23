# Project Requirements: Email Spam Detection

## 1. Technical Dependencies (`requirements.txt`)
If you are running this locally (outside of Google Colab), you will need to install the following Python packages. You can install them by running `pip install -r requirements.txt`.

```text
pandas
scikit-learn
```
*(Note: Google Colab comes with these packages pre-installed, so you don't need to install them if you are using Colab).*

---

## 2. Functional Requirements
These are the core capabilities the project was built to deliver:

### Data Collection
- **Requirement:** The system must be able to automatically fetch the SMS Spam Collection dataset from a public source to avoid manual file uploads.
- **Implementation:** Uses Python's built-in `urllib.request` to pull the `.tsv` file.

### Data Processing
- **Requirement:** The system must process raw text data into numerical features suitable for machine learning.
- **Implementation:** Utilizes `TfidfVectorizer` to convert text strings into TF-IDF (Term Frequency-Inverse Document Frequency) matrices, while filtering out common English stop words.

### Model Training
- **Requirement:** The system must train a classification model capable of distinguishing between "Spam" and "Ham" (Not Spam).
- **Implementation:** Uses the `MultinomialNB` (Multinomial Naive Bayes) algorithm, which is highly efficient for text-based classification.

### Evaluation & Metrics
- **Requirement:** The system must provide objective metrics to evaluate the model's performance on unseen data.
- **Implementation:** Splits the data (80/20) and outputs the Accuracy Score, a Confusion Matrix, and a detailed Classification Report (Precision, Recall, F1-score) to the terminal.

### Interactive Inference
- **Requirement:** The user must be able to input custom text strings to test the model's predictions in real-time.
- **Implementation:** Includes an interactive loop where a list of custom strings is transformed and passed to the trained model, with human-readable results printed to the terminal output.
