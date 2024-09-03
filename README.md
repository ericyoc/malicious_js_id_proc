# Malicious JavaScript Classification with Obfuscation Analysis

This project aims to classify malware and evaluate the impact of obfuscation techniques on model performance. The provided Python script utilizes machine learning techniques to preprocess data, train a neural network, and optimize hyperparameters.

## Motivating Articles

Aryal, K., Gupta, M., & Abdelsalam, M. (2021). A survey on adversarial attacks for malware analysis. arXiv preprint arXiv:2111.08223.
https://arxiv.org/abs/2111.08223

### Older Work

X. He, L. Xu and C. Cha, "Malicious JavaScript Code Detection Based on Hybrid Analysis," 2018 25th Asia-Pacific Software Engineering Conference (APSEC), Nara, Japan, 2018, pp. 365-374, doi: 10.1109/APSEC.2018.00051.
https://ieeexplore.ieee.org/abstract/document/8719574

Wang, Y., Cai, W. D., & Wei, P. C. (2016). A deep learning approach for detecting malicious JavaScript code. Security and Communication Networks, 9(11), 1520-1534.
https://onlinelibrary.wiley.com/doi/abs/10.1002/sec.1441

## Overview

The script performs the following key tasks:

1. **Data Loading and Preprocessing**:
   - Loads category and metadata datasets from CSV files.
   - Applies various levels of obfuscation to the data to simulate real-world scenarios where features might be obscured.

2. **Model Training**:
   - Constructs a neural network model using TensorFlow/Keras.
   - Optimizes model hyperparameters (e.g., layer sizes, learning rate) through grid search.

3. **Evaluation and Visualization**:
   - Evaluates the model's performance on a test set for each obfuscation level.
   - Plots training and validation accuracy to visualize the effects of obfuscation on model performance.

## Datasets

BODMAS: An Open Dataset for Learning based Temporal Analysis of PE Malware
Limin Yang, Arridhana Ciptadi, Ihar Laziuk, Ali Ahmadzadeh, Gang Wang
4th Deep Learning and Security Workshop, 2021
https://whyisyoung.github.io/BODMAS/

### `bodmas_malware_category.csv`
- **Description**: Contains malware samples with categories.
- **Columns**:
  - `sha256`: Unique hash of the sample.
  - `category`: Malware category (e.g., 'worm').

### `bodmas_metadata.csv`
- **Description**: Contains metadata associated with malware samples.
- **Columns**:
  - `sha`: Unique hash of the sample.
  - `timestamp`: Time of the sample's creation.
  - `family`: Malware family.

## Code and Functionality

### Data Loading and Preprocessing
- **Feature Extraction**: Currently uses simple methods like string length. Future improvements could involve more advanced feature extraction techniques.
- **Obfuscation Techniques**: Implements basic obfuscation (noise addition, random characters, feature shuffling). More realistic and diverse obfuscation methods could enhance the analysis.

### Model Training and Hyperparameter Optimization
- **Model Construction**: Uses a neural network with customizable layers and learning rates.
- **Optimization**: Employs grid search to find the best hyperparameters.

### Evaluation and Visualization
- **Metrics**: Evaluates model performance based on accuracy. Including additional metrics such as precision, recall, F1 score, and ROC AUC could provide a more comprehensive assessment.
- **Cross-Validation**: Consider implementing cross-validation for more robust performance evaluation.
- **Plotting**: Visualizes training and validation accuracy across different obfuscation levels.

## Results

The current implementation provides a foundation for evaluating the impact of obfuscation on malware classification. This includes:

1. **Quantifying Obfuscation Impact**:
   - Demonstrates how different obfuscation techniques affect malware classification accuracy.

2. **Optimizing Model Performance**:
   - Identifies effective hyperparameter configurations through grid search.

3. **Evaluating Robustness**:
   - Provides insights into model performance across varying obfuscation levels, helping to assess the robustness of classification techniques.

## Disclaimer
This project and its associated code are provided for educational and research purposes only. The effectiveness of the techniques demonstrated may vary depending on the specific characteristics of the data and the implementation details. Use of the code in production environments or for critical applications should be approached with caution and proper validation. The author is not responsible for any issues or damages that may arise from the use of this code.
