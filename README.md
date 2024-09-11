# Email Spam and Ham Classification

# Project Overview

This project aims to classify emails into 'Spam' and 'Ham' (Non-Spam) using machine learning techniques. The model takes email text as input and predicts whether the email is spam or not, by implementing various natural language processing and classification algorithms.

# Table of Contents

1. [Data](#data)
2. [Preprocessing](#preprocessing)
3. [Modeling](#modeling)
4. [Evaluation](#evaluation)
5. [How to Run](#how-to-run)
6. [Conclusion](#conclusion)

# Data

The dataset used for this project is the **SMSSpamCollection**, which contains labeled messages (email content) categorized into two classes: 'spam' and 'ham'. The dataset consists of 5574 records.

- Labels: 'spam' for spam messages and 'ham' for non-spam messages.
- Features: Email message content.

After balancing the data, we used 1000 ham messages and 747 spam messages for the final dataset.

# Preprocessing

Key preprocessing steps include:

1. Text Cleaning:
   - Removed special characters, numbers, and HTML tags using regular expressions.
   - Converted the text to lowercase.
   
2. Feature Extraction:
   - Applied **Bag of Words** using `CountVectorizer` to convert text data into numerical features.
   - Used the top 1500 most frequent words as features.

3. Label Encoding:
   - Encoded 'spam' as 1 and 'ham' as 0.

# Modeling

Three Naive Bayes models were implemented to classify the emails:

1. **Multinomial Naive Bayes**
2. **Bernoulli Naive Bayes**
3. **Gaussian Naive Bayes**

# Model Training

- The dataset was split into training and testing sets with an 85-15 ratio.
- Each model was trained on the training set.
  
# Model Results

| Model                     | Training Accuracy | Testing Accuracy |
|----------------------------|-------------------|------------------|
| Multinomial Naive Bayes     | 96.83%            | 93.15%           |
| Bernoulli Naive Bayes       | 96.29%            | 93.92%           |
| Gaussian Naive Bayes        | 98.31%            | 91.25%           |

# Evaluation

The model performance was evaluated using a **confusion matrix** and **classification report**.

- **Precision, Recall, F1-Score** were computed for both the spam and ham classes.
  
Confusion Matrix:
```
array([[138,   6],
       [ 12, 107]], dtype=int64)
```

- **Accuracy**: 93% overall on the testing dataset.
  
A heatmap for the confusion matrix was plotted for visualization.

## How to Run

### Prerequisites

- Python 3.x
- Install the dependencies using:
  ```
  pip install -r requirements.txt
  ```

# Running the Project

1. Clone the repository.
2. Navigate to the project directory.
3. Run the main script.

This will load the pre-trained models and the vectorizer to classify new emails as spam or ham.

# Conclusion

The **Multinomial Naive Bayes** and **Bernoulli Naive Bayes** models performed well in this email classification task. This project demonstrates the effectiveness of Naive Bayes algorithms in text classification problems. Future improvements may include experimenting with different text vectorization techniques (like TF-IDF) and using more sophisticated models like SVM or deep learning.
