Cryptographic Misuse Detection Using Machine Learning
This project aims to detect cryptographic misuse in Java code by analyzing patterns of cryptographic API usage. The workflow involves parsing Java code, extracting cryptographic features, and applying machine learning models to classify the code as either secure or misuse based on its cryptographic practices.


Project Overview
Cryptographic misuse is a common security vulnerability in software. This project focuses on detecting improper cryptographic practices in Java code, such as using weak algorithms (e.g., MD5, SHA1) or insecure providers. By applying machine learning models to extracted features from cryptographic API calls, the project aims to classify code as either secure or misuse.

Features
Java Code Parsing: Parse Java code snippets using the javalang library.
Feature Extraction: Automatically extract cryptographic API usage (e.g., algorithms, methods, providers) from Java code.
Machine Learning: Train models to classify cryptographic usage as either secure or misuse.
Evaluation: Measure model performance using metrics such as accuracy, precision, recall, F1-score, and confusion matrix.
Visualization: Generate a confusion matrix to visualize model performance.
Support for Secure and Misuse Classification: Analyze both cryptographic misuse and secure practices.
Installation
To run this project locally, follow these steps:
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Required Python Libraries:

pandas
javalang
scikit-learn
matplotlib
xgboost (for alternative models)
imblearn (for handling class imbalance, if needed)
(Optional) Create a virtual environment:

bash
Copy code
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
Data
The project uses two types of data:

Cryptographic Misuse Code: Java code snippets that demonstrate improper cryptographic usage, such as weak algorithms or insecure providers.
Secure Cryptographic Code: Java code snippets that demonstrate best practices in cryptographic usage.
The Java code snippets should be provided in the following format:

research/crypto_misuse_code_snippets.zip: Contains the misuse and secure Java code snippets.
Make sure to place your .zip file in the correct path or modify the script to point to your dataset location.

Usage
To run the project and extract cryptographic features:

Extract Features from Java Code:

Extract features like algorithms, methods, and providers from the Java code.
Run the script:
bash
Copy code
python feature_extraction.py
Train and Evaluate Machine Learning Models:

Train machine learning models to classify code snippets as secure or misuse.
Run the training script:
bash
Copy code
python train_model.py
Generate Confusion Matrix:

Use the confusion matrix to visualize model performance.
You can modify confusion_matrix.py to run this step:
bash
Copy code
python confusion_matrix.py
Model Training
Random Forest Classifier: The project initially uses a RandomForestClassifier to classify cryptographic usage.
XGBoost: You can experiment with XGBoost or other classifiers like SVM, Logistic Regression, etc.
Feature Engineering: Add more features such as key sizes, cipher modes, or additional cryptographic details.
Evaluation
You can evaluate the model performance using:

Accuracy: The proportion of correctly classified instances.
Precision: The accuracy of positive predictions (misuse cases).
Recall: The proportion of actual misuse cases that were correctly predicted.
F1-Score: The harmonic mean of precision and recall, balancing the two.
Confusion Matrix: Visualizes the true positives, true negatives, false positives, and false negatives.
Future Work
Feature Expansion: Add more cryptographic-related features, such as key sizes, cipher modes, padding schemes, and exception handling.
Hyperparameter Tuning: Experiment with hyperparameter optimization techniques like GridSearchCV or RandomizedSearchCV to improve model performance.
Support for Other Programming Languages: Expand the project to support cryptographic misuse detection in other languages like Python or C++.
Contributing
Contributions are welcome! Please feel free to submit a pull request or open an issue to suggest improvements or new features.
