Enhancing Cryptographic Security Through AST-Based Misuse Detection and Machine Learning
This project implements an SVM-based classifier for detecting cryptographic misuse in software. The tool uses Joern for feature extraction through AST-based analysis and applies machine learning to classify cryptographic operations as secure or insecure.

Overview
Cryptographic misuse can lead to security vulnerabilities. This project enhances the detection of such misuses by combining Joern’s static analysis with an SVM classifier. Two experiments are conducted on labeled datasets to classify cryptographic operations based on features extracted from source code.

Key Features:
AST-based Analysis: Feature extraction using Joern’s Code Property Graph (CPG).
SVM Classifier: Classifies cryptographic operations as secure or insecure.
Evaluation Metrics: Accuracy, Precision, Recall, and F1-Score.
Visualization: Histograms of secure vs insecure instances.
Installation
Ensure Python 3.x is installed. Install required Python libraries:

bash
Copy code
pip install pandas scikit-learn matplotlib numpy
Joern Setup
Download and install Joern following the official guide.

Parse source code to generate CPG:

bash
Copy code
./joern-parse your_source_code_directory --output=cpg.bin
Extract features (e.g., method calls):

bash
Copy code
joern> cpg.method.call.name.p
Export features to a format compatible with the SVM classifier.

Running the Classifier
Prepare datasets with code snippets and labels (0 for secure, 1 for insecure). Optionally, include Joern-extracted features.

Train the SVM classifier:

For Experiment 1:

bash
Copy code
python experiment1_svm.py
For Experiment 2:

bash
Copy code
python experiment2_svm.py
The classifier will output Accuracy, Precision, Recall, and F1-Score, along with a detailed classification report.

Dataset
Ensure the dataset is in CSV format with the following structure:

code: Cryptographic code snippet.
label: Classification (0 = secure, 1 = insecure).
(Optional): Features extracted from Joern.
Results
Accuracy: Overall performance of the classifier.
Precision: Correctness of insecure predictions.
Recall: The ability to detect insecure instances.
F1-Score: Balances Precision and Recall.
The results include visualizations showing secure vs insecure instances for cryptographic misuse categories.
