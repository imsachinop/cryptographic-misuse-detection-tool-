# Cryptographic Misuse Detection Using Machine Learning

This project focuses on detecting cryptographic misuse in Java code by analyzing cryptographic API usage patterns. The project uses machine learning to classify Java code snippets as either **secure** or **misuse** based on cryptographic practices.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Data](#data)
- [Usage](#usage)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Future Work](#future-work)
- [Contributing](#contributing)

## Project Overview
The goal of this project is to identify improper cryptographic practices in Java code, such as using weak algorithms (e.g., `MD5`, `SHA1`) or insecure providers. By extracting features from cryptographic API calls and applying machine learning, the model classifies whether the cryptography in the code is **secure** or **misused**.

## Features
- **Java Code Parsing**: Uses `javalang` to parse Java code and extract cryptographic API usage.
- **Feature Extraction**: Automatically extracts key cryptographic details (algorithms, methods, and providers).
- **Machine Learning**: Trains models to classify cryptographic usage as either secure or misuse.
- **Evaluation Metrics**: Provides accuracy, precision, recall, F1-score, and confusion matrix for model performance.

## Data
The project requires two types of Java code snippets:
1. **Cryptographic Misuse Code**: Examples of improper cryptographic usage.
2. **Secure Cryptographic Code**: Examples demonstrating secure cryptographic practices.

These snippets are stored in a `.zip` file (`research/crypto_misuse_code_snippets.zip`), which contains the Java files used for analysis.

## Usage
1. **Feature Extraction**: Extract cryptographic features from Java files using:
   ```bash
   python feature_extraction.py
Model Training: Train machine learning models to classify code snippets:

bash
Copy code
python train_model.py
Evaluate Model Performance: Generate a confusion matrix to visualize the model's classification results:

bash
Copy code
python confusion_matrix.py
Model Training
The project uses:

### RandomForestClassifier: As the baseline classifier for detecting cryptographic misuse.
### XGBoost: An alternative model used to enhance classification performance.
To train the models, the extracted cryptographic features (e.g., algorithms, methods, providers) are used as input data. These features are numerically encoded and fed into the machine learning models. The classifier is trained to detect cryptographic misuse based on the extracted features.

## Evaluation
The model's performance is evaluated using the following metrics:

Accuracy: Measures how often the model correctly classifies code snippets.
Precision: Measures the proportion of code snippets predicted as misuse that were actually misuse.
Recall: Measures how well the model identifies actual misuse cases.
F1-Score: A balanced measure that combines precision and recall.
The evaluation results, including the confusion matrix, help understand the model's ability to distinguish between secure and misuse cases in cryptographic usage.

## Future Work
Feature Expansion: Add more cryptographic features such as key sizes, cipher modes, padding schemes, and security-related flags.
Hyperparameter Tuning: Use techniques like GridSearchCV to fine-tune model hyperparameters for better performance.
Additional Models: Experiment with alternative machine learning models like Support Vector Machines (SVM) or Gradient Boosting (e.g., LightGBM or XGBoost).
Cross-language Support: Extend the project to support other programming languages such as Python or C++ for cryptographic misuse detection.
## Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request if you'd like to improve the project or add new features.
