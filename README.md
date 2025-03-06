
# Spam Email Classifier

A machine learning project to detect spam emails using a Naive Bayes model trained on the UCI Spambase dataset. This project demonstrates skills in data preprocessing, model training, evaluation, and custom feature extraction for email classification, making it a strong addition to any data science or ML portfolio.

## Features
- **Training**: Multinomial Naive Bayes model trained on the UCI Spambase dataset, achieving ~95% F1-score.
- **Prediction Methods**:
  1. **Manual Feature Input**: Classify emails using predefined 57-feature vectors mimicking Spambase data.
  2. **Raw Text Processing**: Extract Spambase-compatible features from raw email text for prediction.
- **Evaluation**: Generates a confusion matrix and detailed metrics (accuracy, precision, recall, F1-score).

## Project Structure
spam-email-classifier/
├── data/
│   └── spambase.data         # UCI Spambase dataset
├── src/
│   ├── train.py             # Trains the model and saves it as model.pkl
│   ├── predict_manual.py    # Predicts using manual feature input
│   ├── predict_text.py      # Predicts using raw email text input
│   └── model.pkl            # Trained Naive Bayes model
├── notebooks/
│   └── explore.ipynb        # Optional data exploration notebook
├── README.md                # Project documentation (this file)
├── requirements.txt         # Python dependencies
└── .gitignore               # Ignores unnecessary files


## Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/<your-username>/spam-email-classifier.git
   cd spam-email-classifier
Replace <your-username> with your GitHub username.

Install Dependencies:
bash

Collapse

Wrap

Copy
pip install -r requirements.txt
Required libraries include pandas, scikit-learn, matplotlib, and seaborn.
Download the Dataset:
Download spambase.data from the UCI Spambase Dataset.
Place it in the data/ directory.
Usage
1. Train the Model
Train the Naive Bayes model and save it as model.pkl:

bash
python src/train.py

Outputs:
Performance metrics (e.g., precision, recall, F1-score).
A confusion matrix saved as confusion_matrix.png in src/.

2. Predict with Manual Feature Input
Classify an email using a hardcoded 57-feature vector:

bash

Collapse

Wrap

Copy
python src/predict_manual.py
Example: Sets word_freq_free to 1.0 and word_freq_money to 0.5 to simulate spam-like features.
Output: "Spam" or "Ham".
3. Predict with Raw Text
Process raw email text into Spambase features and classify:

bash

python src/predict_text.py
Prompts you to enter email text (e.g., "Win a FREE iPhone NOW! Click here!!!").
Extracts features like word frequencies, character frequencies, and capital run lengths.
Output: The input text and its prediction ("Spam" or "Ham").

Results

Training Performance:

Accuracy: ~95% on the Spambase test set.
F1-Score: ~0.95 for ham, ~0.89 for spam (exact values may vary slightly).
Evaluation Visualization: Check confusion_matrix.png in src/ for a graphical breakdown of predictions.

How It Works
Dataset: The UCI Spambase dataset contains 4601 email samples with 57 pre-extracted features (e.g., frequency of "free," "!", capital run lengths) and a binary label (0 = ham, 1 = spam).
Model: Multinomial Naive Bayes, chosen for its effectiveness with frequency-based data.
Manual Prediction: Uses a predefined 57-feature vector to match Spambase’s format.
Text Prediction: Custom feature extraction converts raw text into the 57 features required by the model, including word frequencies (e.g., "money"), character frequencies (e.g., "!"), and capital run statistics.

Example Output
Manual Prediction
text

Collapse

Wrap

Copy
Prediction: Spam
Text Prediction
text

Text Input: Win a FREE iPhone NOW! Click here!!!
Prediction: Spam


Future Enhancements
API Integration: Add Gmail API or Microsoft Graph API to fetch and classify real emails from an inbox.
Model Comparison: Experiment with alternative algorithms (e.g., Logistic Regression, SVM, or BERT).
Deployment: Create a Flask web app for an interactive demo of spam detection.
Improved Text Processing: Use NLP tools (e.g., NLTK stemming) for more accurate feature extraction.


Requirements
Python 3.6+
Dependencies listed in requirements.txt:
text

pandas
scikit-learn
matplotlib
seaborn

Installation Notes

Ensure spambase.data is in data/ before running train.py.
Run scripts from the project root or adjust file paths in the code if needed.

Limitations

Text Prediction Accuracy: The raw text method approximates Spambase features, so real-world email performance may differ from the training dataset.
Static Features: Limited to the 57 features defined by Spambase (e.g., no URL detection or sender analysis yet).
Contributing
Feel free to fork this repository, submit pull requests, or suggest improvements via issues!

License
This project is licensed under the MIT License - see the LICENSE file for details (create one if desired).

Author
Januki Manage (optional: add GitHub link, email, etc.)
Created: March 2025
