# Malware Dataset Classification with Obfuscation and Deobfuscation 

This project aims to classify a malware dataset and evaluate the impact of obfuscation techniques on model performance. It utilizes machine learning techniques to preprocess data, train neural networks, and optimize hyperparameters, with a focus on comparing obfuscated and deobfuscated malware dataset classification outcomes.

## Motivating Articles

- Aryal, K., Gupta, M., & Abdelsalam, M. (2021). [A survey on adversarial attacks for malware analysis](https://arxiv.org/abs/2111.08223). arXiv preprint arXiv:2111.08223.

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

BODMAS dataset:

Yang, L., Ciptadi, A., Laziuk, I., Ahmadzadeh, A., & Wang, G. (2021). [BODMAS: An Open Dataset for Learning based Temporal Analysis of PE Malware](https://whyisyoung.github.io/BODMAS/). 4th Deep Learning and Security Workshop.

- `bodmas_malware_category.csv`: Contains malware samples with categories.
- `bodmas_metadata.csv`: Contains metadata associated with malware samples.

BODMAS is a dataset released in collaboration with Blue Hexagon, containing 57,293 malware samples and 77,142 benign samples collected between August 2019 and September 2020, with detailed family information for research purposes.

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

### Statistical Significance Testing

Statistical significance testing was conducted to compare the model's performance between obfuscated and deobfuscated datasets. In the test, an F-statistic of `1.588` was calculated, with a p-value of `0.254`. This suggests that the differences in performance between the obfuscated and deobfuscated datasets are not statistically significant, indicating that obfuscation did not have a large impact on the model's ability to classify the malware.

## Results

The implementation provides:

- Quantification of obfuscation impact on malware classification accuracy.
- Comparison between obfuscated and deobfuscated data performance.
- Optimized model hyperparameters through grid search.
- Insights into model robustness across varying obfuscation levels.
- Statistical analysis of the differences between obfuscated and deobfuscated results.

### Performance Summary

![](https://github.com/ericyoc/malicious_js_id_proc/blob/main/performance_plot.png)

The table below summarizes the performance of the model across different levels of obfuscation and deobfuscation:

| Obfuscation Level |  Data Type   | Accuracy | ROC AUC | Precision | Recall | F1 Score |
|-------------------|--------------|----------|---------|-----------|--------|----------|
|        none       |  obfuscated  |  0.9999  |  1.0000 |   0.9997  | 1.0000 |  0.9998  |
|        none       | deobfuscated |  0.9995  |  0.9999 |   0.9982  | 1.0000 |  0.9991  |
|        low        |  obfuscated  |  0.9999  |  0.9999 |   0.9997  | 1.0000 |  0.9998  |
|        low        | deobfuscated |  0.9999  |  0.9999 |   0.9997  | 1.0000 |  0.9998  |
|       medium      |  obfuscated  |  0.9999  |  0.9999 |   0.9997  | 1.0000 |  0.9998  |
|       medium      | deobfuscated |  0.9998  |  0.9999 |   0.9994  | 1.0000 |  0.9997  |
|        high       |  obfuscated  |  0.9999  |  0.9999 |   0.9997  | 1.0000 |  0.9998  |
|        high       | deobfuscated |  0.9999  |  0.9999 |   0.9997  | 1.0000 |  0.9998  |

These results demonstrate that the model performs consistently well across different obfuscation levels. The minor variations in accuracy, precision, recall, and F1 score indicate a high robustness of the model, suggesting that the obfuscation techniques used do not significantly hinder the model's ability to classify malware accurately.

## Disclaimer

This project and its associated code are provided for educational and research purposes only. The effectiveness of the techniques demonstrated may vary depending on the specific characteristics of the data and the implementation details. Use of the code in production environments or for critical applications should be approached with caution and proper validation. The author is not responsible for any issues or damages that may arise from the use of this code.
