# ECG Arrhythmia Classification using CNN-LSTM on MIT-BIH

## Project Overview

This project builds an ECG heartbeat classifier using the MIT-BIH Arrhythmia Database and deep learning models implemented in PyTorch.

Instead of using preprocessed CSV datasets, the entire pipeline starts from the original MIT-BIH WFDB files (`.dat`, `.hea`, `.atr`) and includes data extraction, preprocessing, heartbeat classification and model evaluation.

The goal was to explore how recurrent neural networks and convolutional neural networks can be used for ECG signal analysis.

---

## Dataset

The project uses the MIT-BIH Arrhythmia Database from PhysioNet.

* 48 ECG recordings
* Each recording is approximately 30 minutes long
* Sampling frequency: 360 Hz
* Two ECG leads per recording
* Expert annotations provided by cardiologists

Each record contains:

* `.dat` files containing the ECG signal
* `.hea` files containing recording information
* `.atr` files containing heartbeat annotations

---

## Data Preparation

### Lead Selection

MIT-BIH recordings contain two ECG leads for most patients.
This project uses only the MLII lead for heartbeat extraction and classification, as it provides prominent QRS complexes and is commonly used in arrhythmia detection studies.

### Heartbeat Extraction

For every annotated heartbeat, a window of 250 samples centered around the R-peak was extracted from the ECG signal.

This produced a dataset containing:

* **109451 heartbeat samples**

---

### AAMI Mapping

The original MIT-BIH labels were converted to the AAMI EC57 heartbeat categories.

| MIT-BIH Labels | AAMI Class |
| -------------- | ---------- |
| N, L, R, e, j  | N          |
| A, a, J, S     | S          |
| V, E           | V          |
| F              | F          |
| /, f, Q        | Q          |

---

### Patient-Level Train/Test Split

To avoid data leakage, the train-test split was performed at the patient level instead of the heartbeat level.

This ensures that heartbeats from a patient in the training set never appear in the test set.

---

### Handling Class Imbalance

After patient-level splitting, the Fusion Beat (F) category contained only:

* 786 training samples
* 16 testing samples

Since evaluation on such a small test set would not be reliable, the final experiments were performed on the remaining four classes:

* N — Normal Beat
* S — Supraventricular Beat
* V — Ventricular Beat
* Q — Unknown/Paced Beat

---

## Models

### LSTM Model

Baseline architecture:

* 2-layer LSTM
* Hidden size: 128
* Dropout: 0.3
* Fully connected output layer

### CNN-LSTM Model

The final model combines convolutional layers with LSTMs.

The convolutional layers learn local ECG patterns such as QRS complexes, while the LSTM captures temporal dependencies in the signal.

Architecture:

```text
Input Beat (250 samples)
        ↓
Conv1D (32 filters)
        ↓
ReLU + MaxPooling
        ↓
Conv1D (64 filters)
        ↓
ReLU + MaxPooling
        ↓
2-layer LSTM
        ↓
Fully Connected Layer
        ↓
Output Class
```

---

## Handling Imbalanced Classes

Three approaches were tested:

1. Weighted Cross Entropy Loss
2. WeightedRandomSampler
3. Combination of both

Weighted Cross Entropy Loss produced the best overall performance and the best balance between majority and minority classes.

---

## Results

Best results obtained using weighted loss:

| Metric         | Value |
| -------------- | ----- |
| Test Accuracy  | 71.3% |
| Macro F1 Score | 0.53  |

Classification report:

| Class | Precision | Recall | F1   |
| ----- | --------- | ------ | ---- |
| N     | 0.96      | 0.71   | 0.82 |
| S     | 0.05      | 0.49   | 0.09 |
| V     | 0.33      | 0.90   | 0.48 |
| Q     | 0.77      | 0.68   | 0.72 |

---

## Libraries Used

* PyTorch
* Python
* NumPy
* Scikit-Learn
* WFDB
* Matplotlib

---

## Future Improvements

Possible future directions:

* Bidirectional LSTM
* Attention mechanisms
* Focal Loss
* Transformer-based models
* Multi-lead ECG classification

---

## References

* MIT-BIH Arrhythmia Database
* WFDB Python Package
* AAMI EC57 Standard
