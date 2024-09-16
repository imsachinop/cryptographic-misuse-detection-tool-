#Enhancing Cryptographic Security Through AST-Based Misuse Detection and Machine Learning
This repository contains an implementation for detecting cryptographic misuse in software using AST-based (Abstract Syntax Tree) static analysis and machine learning techniques. The tool leverages Joern for code feature extraction and an SVM (Support Vector Machine) classifier to differentiate between secure and insecure cryptographic operations.

Project Overview
Cryptographic misuse is a prevalent issue in software security that can lead to severe vulnerabilities. This project enhances the detection of cryptographic misuses by integrating static analysis using Joern and a supervised learning classifier (SVM). We perform two experiments to classify cryptographic operations as either secure or insecure based on labeled datasets.

Features:
AST-based Static Analysis: Extraction of structural features from code snippets using Joern's Code Property Graph (CPG).
SVM Classifier: Classifies cryptographic operations as secure or insecure based on extracted features.
Evaluation Metrics: Accuracy, Precision, Recall, and F1-Score are computed to evaluate classifier performance.
Visualization: Results are visualized using histograms showing secure vs insecure instances across cryptographic misuse categories.
Table of Contents
Installation
Joern Setup
Running the Classifier
Experiments
Experiment 1
Experiment 2
Results
Dataset
Contributing
License
Installation
To run this project locally, you will need Python 3.x and the following Python libraries:

pandas
scikit-learn
matplotlib
numpy
Install the dependencies using pip:

bash
Copy code
pip install pandas scikit-learn matplotlib numpy
Joern Setup
Joern is a cutting-edge static analysis tool that generates Code Property Graphs (CPGs) to extract structural and semantic features from source code. Follow these steps to set up Joern:

1. Install Joern
Download and install Joern by following the official installation guide. For Unix systems:

bash
Copy code
curl -L https://github.com/joernio/joern/releases/download/v1.1.123/joern-install.sh | sh
./joern/joern
2. Parse Source Code to Generate CPG
Once installed, use Joern to generate a CPG (Code Property Graph) from your source code. Example:

bash
Copy code
./joern-parse your_source_code_directory --output=cpg.bin
3. Extract Features Using Joern
Extract relevant features from the code such as method invocations, control flow, and data flow. For example:

bash
Copy code
joern> cpg.method.call.name.p
4. Export Joern Features
After extracting the desired features, export them to a CSV file (or another format) that can be used as input for the machine learning classifier.

Running the Classifier
Dataset Requirements
You will need two datasets (one for each experiment) in CSV format. Each dataset should contain at least:

code: Code snippets related to cryptographic operations.
label: Binary labels where 0 indicates secure use and 1 indicates insecure use.
Optionally, enrich the dataset with Joern-extracted features (e.g., method calls, control flow) to enhance the classifier's input.

Training the Classifier
Experiment 1:
To train the classifier for Experiment 1 using your dataset and Joern features, run:

bash
Copy code
python experiment1_svm.py
Experiment 2:
To train the classifier for Experiment 2, run:

bash
Copy code
python experiment2_svm.py
Classifier Workflow:
The dataset is loaded, and features are extracted from the code snippets using TF-IDF or Joern-based features.
The data is split into training and test sets.
An SVM classifier is trained to classify cryptographic operations as secure or insecure.
The model performance is evaluated using metrics such as Accuracy, Precision, Recall, and F1-Score.
A detailed classification report is provided, and the results are visualized.
Experiments
Experiment 1:
In Experiment 1, the classifier is trained on a dataset that contains labeled cryptographic operations across categories such as:

Weak Cryptography
Poor Key Management
Bad Randomness
Program Design Flaws
Improper Certificate Validation
Coding and Implementation Bugs
The dataset is evaluated for secure vs insecure classification.

Experiment 2:
Experiment 2 follows a similar approach but uses a different dataset with cryptographic misuse categories such as:

Cipher
Hash
IV/Nonce Management
TLS and Key Management
Example of Secure vs Insecure RSA Usage:
The project also includes real-world examples of secure and insecure cryptographic operations (e.g., RSA with and without padding) to help identify misuse cases.

Results
The classifier performance is evaluated using the following metrics:

Accuracy: The overall correctness of the model.
Precision: How many of the predicted insecure instances are actually insecure.
Recall: How many of the actual insecure instances are correctly identified.
F1-Score: The harmonic mean of Precision and Recall, providing a balanced measure of both.
Histograms showing the secure and insecure instances for various cryptographic categories are also provided for both experiments.

Dataset
The dataset for this project should contain labeled cryptographic misuse cases. It should be in CSV format and include the following columns:

code: The cryptographic operation in code format.
label: The classification label (0 for secure, 1 for insecure).
(Optional): Features extracted using Joern such as method calls, control flow, or data flow.
You can either use a pre-existing dataset or create one by parsing cryptographic code through Joern to extract features.

Contributing
Contributions to this project are welcome. If you'd like to contribute:

Fork the repository.
Create a feature branch (git checkout -b feature-branch).
Commit your changes (git commit -m "Add new feature").
Push to the branch (git push origin feature-branch).
Create a Pull Request.
