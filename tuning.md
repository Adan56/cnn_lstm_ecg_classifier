label2idx = {'N': 0, 'S': 1, 'V': 2, 'F': 3, 'Q': 4}



##### without considering weight imbalance and without standardisation (learning rate = 0.005)

Epoch 20/20 | Loss: 0.0498 | Train Acc: 0.9866 | Test Acc: 0.8803

&#x09;	precision    recall  f1-score   support



&#x20;          0       0.96      0.91      0.93     19214

&#x20;          1       0.04      0.09      0.06       411

&#x20;          2       0.46      0.93      0.61       800

&#x20;          3       0.00      0.00      0.00        16

&#x20;          4       0.91      0.76      0.83      2066



&#x20;   accuracy                           0.88     22507

&#x20;  macro avg       0.47      0.54      0.49     22507

weighted avg       0.92      0.88      0.90     22507



##### without considering weight imbalance but with standardisation (learning rate = 0.005)

Epoch 20/20 | Loss: 0.0542 | Train Acc: 0.9850 | Test Acc: 0.8333

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.89      0.92      0.91     19214

&#x20;          1       0.08      0.10      0.09       411

&#x20;          2       0.53      0.68      0.59       800

&#x20;          3       0.00      0.06      0.00        16

&#x20;          4       0.66      0.20      0.31      2066



&#x20;   accuracy                           0.83     22507

&#x20;  macro avg       0.43      0.39      0.38     22507

weighted avg       0.84      0.83      0.83     22507





##### without considering weight imbalance but with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0498 | Train Acc: 0.9862 | Test Acc: 0.8425

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.90      0.92      0.91     19214

&#x20;          1       0.01      0.00      0.01       411

&#x20;          2       0.48      0.78      0.59       800

&#x20;          3       0.00      0.06      0.01        16

&#x20;          4       0.58      0.31      0.40      2066



&#x20;   accuracy                           0.84     22507

&#x20;  macro avg       0.39      0.42      0.38     22507

weighted avg       0.84      0.84      0.84     22507





### Now, considering weight imbalance

##### using weight sampler in loss calculation with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.2594 | Train Acc: 0.9015 | Test Acc: 0.5755

&#x09;	precision    recall  f1-score   support



&#x20;          0       0.87      0.62      0.72     19214

&#x20;          1       0.04      0.44      0.08       411

&#x20;          2       0.44      0.62      0.52       800

&#x20;          3       0.00      0.19      0.00        16

&#x20;          4       0.29      0.16      0.21      2066



&#x20;   accuracy                           0.58     22507

&#x20;  macro avg       0.33      0.41      0.31     22507

weighted avg       0.78      0.58      0.66     22507





##### using WeightedRandomSampler in dataloader with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0618 | Train Acc: 0.9799 | Test Acc: 0.6349

&#x09;	precision    recall  f1-score   support



&#x20;          0       0.93      0.69      0.79     19214

&#x20;          1       0.04      0.41      0.08       411

&#x20;          2       0.36      0.82      0.50       800

&#x20;          3       0.00      0.06      0.00        16

&#x20;          4       0.46      0.14      0.21      2066



&#x20;   accuracy                           0.63     22507

&#x20;  macro avg       0.36      0.42      0.32     22507

weighted avg       0.85      0.63      0.71     22507



##### using sampler both in loss calculation and dataloader with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0707 | Train Acc: 0.8153 | Test Acc: 0.1625

&#x09;	precision    recall  f1-score   support



&#x20;          0       0.97      0.09      0.17     19214

&#x20;          1       0.02      0.59      0.04       411

&#x20;          2       0.24      0.79      0.37       800

&#x20;          3       0.00      0.12      0.00        16

&#x20;          4       0.54      0.47      0.50      2066



&#x20;   accuracy                           0.16     22507

&#x20;  macro avg       0.35      0.41      0.22     22507

weighted avg       0.88      0.16      0.21     22507







### CNN-LSTM model

##### without considering weight imbalance but with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0241 | Train Acc: 0.9925 | Test Acc: 0.8270

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.93      0.87      0.90     19214

&#x20;          1       0.08      0.09      0.09       411

&#x20;          2       0.32      0.83      0.46       800

&#x20;          3       0.00      0.00      0.00        16

&#x20;          4       0.81      0.57      0.67      2066



&#x20;   accuracy                           0.83     22507

&#x20;  macro avg       0.43      0.47      0.42     22507

weighted avg       0.88      0.83      0.85     22507



##### using weight sampler in loss calculation with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.1219 | Train Acc: 0.9494 | Test Acc: 0.6721

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.96      0.70      0.81     19214

&#x20;          1       0.07      0.40      0.12       411

&#x20;          2       0.24      0.65      0.35       800

&#x20;          3       0.00      0.12      0.00        16

&#x20;          4       0.53      0.46      0.49      2066



&#x20;   accuracy                           0.67     22507

&#x20;  macro avg       0.36      0.47      0.36     22507

weighted avg       0.88      0.67      0.75     22507



##### using WeightedRandomSampler in dataloader with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0279 | Train Acc: 0.9910 | Test Acc: 0.6755

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.93      0.72      0.81     19214

&#x20;          1       0.06      0.40      0.10       411

&#x20;          2       0.20      0.72      0.32       800

&#x20;          3       0.00      0.06      0.00        16

&#x20;          4       0.63      0.27      0.38      2066



&#x20;   accuracy                           0.68     22507

&#x20;  macro avg       0.36      0.43      0.32     22507

weighted avg       0.86      0.68      0.74     22507



##### using sampler both in loss calculation and dataloader with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0188 | Train Acc: 0.9461 | Test Acc: 0.3743

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.86      0.38      0.53     19214

&#x20;          1       0.04      0.56      0.07       411

&#x20;          2       0.27      0.65      0.38       800

&#x20;          3       0.00      0.12      0.00        16

&#x20;          4       0.22      0.16      0.19      2066



&#x20;   accuracy                           0.37     22507

&#x20;  macro avg       0.28      0.37      0.23     22507

weighted avg       0.77      0.37      0.48     22507





### Note:

***MIT-BIH annotations were mapped to AAMI EC57 classes: N, S, V, F, Q***

***After patient-level splitting, the F (Fusion Beat) class contained only 786 training samples and 16 test samples. Due to insufficient samples, the final model was trained on the remaining four classes: N, S, V and Q.***



***label2idx = {'N': 0, 'S': 1, 'V': 2, 'Q': 3}***



##### without considering weight imbalance but with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0177 | Train Acc: 0.9947 | Test Acc: 0.8778

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.95      0.91      0.93     19214

&#x20;          1       0.10      0.08      0.09       411

&#x20;          2       0.35      0.90      0.50       800

&#x20;          3       0.91      0.72      0.80      2066



&#x20;   accuracy                           0.88     22491

&#x20;  macro avg       0.58      0.65      0.58     22491

weighted avg       0.91      0.88      0.89     22491





##### using weight sampler in loss calculation with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0748 | Train Acc: 0.9661 | Test Acc: 0.7133

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.96      0.71      0.82     19214

&#x20;          1       0.05      0.49      0.09       411

&#x20;          2       0.33      0.90      0.48       800

&#x20;          3       0.77      0.68      0.72      2066



&#x20;   accuracy                           0.71     22491

&#x20;  macro avg       0.53      0.70      0.53     22491

weighted avg       0.90      0.71      0.78     22491



##### using WeightedRandomSampler in dataloader with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0137 | Train Acc: 0.9958 | Test Acc: 0.7259

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.95      0.76      0.84     19214

&#x20;          1       0.08      0.38      0.13       411

&#x20;          2       0.19      0.93      0.32       800

&#x20;          3       0.66      0.44      0.53      2066



&#x20;   accuracy                           0.73     22491

&#x20;  macro avg       0.47      0.63      0.46     22491

weighted avg       0.88      0.73      0.78     22491



##### using sampler both in loss calculation and dataloader with standardisation (learning rate = 0.001)

Epoch 20/20 | Loss: 0.0099 | Train Acc: 0.9784 | Test Acc: 0.5969

&#x20;             precision    recall  f1-score   support



&#x20;          0       0.95      0.58      0.72     19214

&#x20;          1       0.05      0.55      0.09       411

&#x20;          2       0.25      0.91      0.39       800

&#x20;          3       0.43      0.63      0.51      2066



&#x20;   accuracy                           0.60     22491

&#x20;  macro avg       0.42      0.67      0.43     22491

weighted avg       0.86      0.60      0.68     22491



