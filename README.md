**spam-mail-detection**

This project implements a robust machine learning system to classify SMS messages as either Ham (legitimate) or Spam. By combining traditional text vectorization with custom-engineered behavioral features, the model achieves high accuracy and reliability.

**Problem Statement**

The objective of this project is to develop a predictive model that accurately filters out harmful spam messages while ensuring legitimate communications are never misclassified. This is achieved by analyzing both the semantic content of the messages and their structural patterns.

**Approach**

The project follows a comprehensive data science workflow, incorporating advanced feature engineering and a hybrid modeling strategy:

**1. Feature Engineering**

Beyond the raw text,I engineered many features to capture the distinct style of spam messages:

**Message Length**: Word count per message.

**Symbol Density**: The ratio of non-alphanumeric characters to message length.

**Currency Count**: Detection of financial symbols ($, €, etc.), which are common in scams.

**Digit Density**: The proportion of numbers, often representing phone numbers or prize amounts.

**Caps Group Count**: Sequences of capital letters to detect "shouting" or emphasis.

**Urgent Word Count**: Occurrences of high-trigger keywords like "Free," "Winner," and "Claim."

**2. Preprocessing & Pipeline**

A **ColumnTransformer** was used to handle multiple data types simultaneously within a Scikit-Learn Pipeline:

**Text Data**: Processed using TfidfVectorizer (with English stop-word removal) to extract semantic meaning.

**Numerical Data**: Scaled using StandardScaler to ensure all engineered features contribute equally to the model.

**3. Model Building**

A Linear Support Vector Machine (SVM) was selected for classification due to its high effectiveness in high-dimensional spaces, such as those created by TF-IDF vectorization.

**Results**

The model's performance across all key metrics on the test dataset is as follows:

**Overall Accuracy**: 99.12%

**Mean Cross-Validation Accuracy**: 98.88%

**Ham Recall (Legitimate Messages)**: 100% (0 false positives)

**Spam Precision**: 99%

<img width="536" height="432" alt="image" src="https://github.com/user-attachments/assets/3d015baf-bcd9-4631-bb26-2c955fbaab16" />
