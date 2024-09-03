# Malicious JavaScript Classification

This project aims to classify malware and evaluate the impact of obfuscation techniques on model performance. It utilizes machine learning techniques to preprocess data, train neural networks, and optimize hyperparameters, with a focus on comparing obfuscated and deobfuscated data.

## Motivating Articles

- Aryal, K., Gupta, M., & Abdelsalam, M. (2021). [A survey on adversarial attacks for malware analysis](https://arxiv.org/abs/2111.08223). arXiv preprint arXiv:2111.08223.

### Older Work

- X. He, L. Xu and C. Cha, (2018). [Malicious JavaScript Code Detection Based on Hybrid Analysis](https://ieeexplore.ieee.org/abstract/document/8719574). 25th Asia-Pacific Software Engineering Conference (APSEC), Nara, Japan, pp. 365-374.
- Wang, Y., Cai, W. D., & Wei, P. C. (2016). [A deep learning approach for detecting malicious JavaScript code](https://onlinelibrary.wiley.com/doi/abs/10.1002/sec.1441). Security and Communication Networks, 9(11), 1520-1534.

## Overview

The script performs the following key tasks:

1. **Data Loading and Preprocessing:**
   - Loads category and metadata datasets from CSV files.
   - Applies various levels of obfuscation to the data.
   - Implements a deobfuscation step to compare obfuscated and deobfuscated data.

2. **Model Training:**
   - Constructs a neural network model using TensorFlow/Keras.
   - Utilizes a custom `KerasClassifierWrapper` for compatibility with scikit-learn.
   - Optimizes model hyperparameters through grid search.

3. **Evaluation and Visualization:**
   - Performs cross-validation using `cross_validate_model`.
   - Evaluates the model's performance on test sets for each obfuscation level and data type (obfuscated/deobfuscated).
   - Calculates comprehensive metrics: accuracy, ROC AUC, precision, recall, F1 score.
   - Plots training and validation accuracy to visualize the effects of obfuscation on model performance.
   - Conducts statistical significance testing to compare obfuscated and deobfuscated results.

## Datasets

We use the BODMAS dataset:

Yang, L., Ciptadi, A., Laziuk, I., Ahmadzadeh, A., & Wang, G. (2021). [BODMAS: An Open Dataset for Learning based Temporal Analysis of PE Malware](https://whyisyoung.github.io/BODMAS/). 4th Deep Learning and Security Workshop.

- `bodmas_malware_category.csv`: Contains malware samples with categories.
- `bodmas_metadata.csv`: Contains metadata associated with malware samples.

## Code and Functionality

### Data Loading and Preprocessing
- Implements feature extraction methods.
- Applies obfuscation techniques (noise addition, random characters, feature shuffling).
- Includes a deobfuscation step for comparison.

### Model Training and Hyperparameter Optimization
- Uses a neural network with customizable layers and learning rates.
- Employs grid search to find the best hyperparameters.
- Utilizes `KerasClassifierWrapper` for scikit-learn compatibility.

### Evaluation and Visualization
- Performs cross-validation for robust performance evaluation.
- Calculates comprehensive metrics (accuracy, ROC AUC, precision, recall, F1 score).
- Visualizes training and validation accuracy across different obfuscation levels for both obfuscated and deobfuscated data.
- Conducts statistical significance testing to compare results.

## Results

The implementation provides:

- Quantification of obfuscation impact on malware classification accuracy.
- Comparison between obfuscated and deobfuscated data performance.
- Optimized model hyperparameters through grid search.
- Insights into model robustness across varying obfuscation levels.
- Statistical analysis of the differences between obfuscated and deobfuscated results.

## Future Improvements

- Implement more advanced feature extraction techniques.
- Explore more realistic and diverse obfuscation methods.
- Investigate the use of different neural network architectures.
- Enhance real-time adaptability of the model.
- Incorporate emerging threat vectors in the analysis.

## Disclaimer

This project and its associated code are provided for educational and research purposes only. The effectiveness of the techniques demonstrated may vary depending on the specific characteristics of the data and the implementation details. Use of the code in production environments or for critical applications should be approached with caution and proper validation. The author is not responsible for any issues or damages that may arise from the use of this code.
