# ML-competition--Anomaly-Detection-on-offshore-naturally-flowing-wells-main-
Anomaly Detection on Offshore Naturally Flowing Wells

Participants:

    Mustapha Bashir Garba – Chemical Engineering PhD Student, University of Leeds
    Ahmad Lawal – Computer Engineering PhD Student, De Montfort University, UK
Report Overview

This report details the approach and methodology adopted for anomaly detection in offshore naturally flowing wells. Despite significant efforts in data preprocessing, feature engineering, and model training, the accuracy of the models remained below 10%. Below, we outline our process, highlight key observations, and discuss potential areas for improvement.

1. Data Organization

Our approach focused on:

    Initial Dataset Structure:
    The raw dataset was structured with temporal and operational features, including sensor readings, flow rates, and timestamps. Each data point represented the state of the well at a specific time.
    Splitting Data:
    The dataset was split into training, validation, and testing subsets to ensure unbiased evaluation of the models. A temporal split was used to simulate real-world conditions by training on earlier data and testing on future data.
    Label Identification:
    Anomalies were identified using labels, which were sparse and imbalanced, reflecting the rare nature of anomalous events in real-world settings.

2. Data Cleaning

The raw data contained inconsistencies and missing values, which required comprehensive cleaning:

    Missing Data Handling:
        Numerical features with missing values were imputed using median imputation, as the median is robust to outliers.
        For categorical variables, the mode or a placeholder category was used.
    Outlier Detection:
    Extreme values that were not labeled as anomalies were capped at domain-specific thresholds to prevent skewing the model.
    Noise Reduction:
    Sensor data with high-frequency noise was smoothed using a rolling average, preserving temporal trends while reducing erratic variations.
    Timestamp Synchronization:
    Temporal data was aligned to ensure consistent time intervals between observations.

3. Feature Engineering

Feature engineering aimed to enhance model interpretability and predictive power:

    Domain-Specific Features:
    Derived features such as pressure gradients, flow consistency ratios, and normalized sensor deviations were created based on domain knowledge.
    Rolling Window Aggregates:
    Temporal features were enriched using rolling windows to compute averages, standard deviations, and rates of change over predefined periods.
    Interaction Features:
    Interactions between key variables (e.g., pressure and flow rate) were introduced to capture non-linear relationships.
    Feature Scaling:
    All features were scaled to a standard range using Min-Max normalization, ensuring comparability across dimensions.
    Dimensionality Reduction:
    Redundant and collinear features were removed using variance inflation factors (VIF) and principal component analysis (PCA).
4. Temporal Split

Anomaly detection models often face challenges due to concept drift and temporal dependencies. To address these:

    Chronological Validation:
    The dataset was split chronologically, with the training set containing earlier data and the test set representing future conditions. This emulates real-world scenarios where models must generalize to unseen future states.
    Sliding Window Approach:
    A sliding window approach was considered to iteratively train and validate the model on overlapping time intervals, ensuring robustness to temporal variations.
5. Model Selection and Training

Several models were experimented with, but none achieved satisfactory accuracy, staying below 10%. Below is a summary of the models and the challenges faced:

    Baseline Models:
        Logistic Regression and Random Forest classifiers were trained as baselines.
        These models struggled with the imbalance and high-dimensionality of the data.
    Anomaly Detection Algorithms:
        Isolation Forest and One-Class SVM were used for unsupervised anomaly detection but performed poorly, likely due to limited representation of anomalies.
    Time-Series Models:
        LSTM networks were employed to capture temporal dependencies. However, they underperformed due to insufficient training data and noise.
    Evaluation Metrics:
        Precision, recall, and F1-score were used to assess performance. High recall was prioritized, but the models suffered from low precision.
  
6. Observations and Challenges

    Data Imbalance:
    The dataset's imbalance (few anomalies compared to normal data) hindered the models' ability to learn effectively.
    Feature Relevance:
    Some features were likely irrelevant or redundant, diluting the signal-to-noise ratio.
    Temporal Variability:
    Temporal drift in the dataset required robust feature engineering, which may not have been sufficiently exhaustive.
    Model Complexity:
    Complex models like LSTM may have overfit the training data due to noise and sparsity in the anomaly labels.

7. Conclusion
Despite the low accuracy, this project provided valuable insights into anomaly detection in offshore naturally flowing wells. It underscored the importance of data preprocessing, feature engineering, and robust validation strategies. While the models fell short of desired performance.
    
