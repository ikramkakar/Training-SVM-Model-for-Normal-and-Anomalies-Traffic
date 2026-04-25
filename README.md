# Training-SVM-Model-for-Normal-and-Anomalies-Traffic

This project trains a Support Vector Machine (SVM) model to classify network traffic as either **normal** or **anomalous**. It uses a synthetic IDS dataset containing features of network flows with annotated labels (`0` = normal, `1` = anomaly).

## Project Structure

- **Training_SVM_Model_for_Normal_and_Anomalies_Traffic.ipynb**: Jupyter Notebook with step-by-step code, explanations, and visualizations.
- **training_svm_model_for_normal_and_anomalies_traffic.py**: Python script version containing the same logic for reproducibility and automation.
- **Network_traffic.csv**: The dataset used for model training and evaluation.

## Workflow Overview

### 1. Data Loading
- The dataset (`Network_traffic.csv`) is loaded into a pandas DataFrame.
- Key features include: `packet_size`, `duration`, `src_bytes`, `dst_bytes`, `random_noise`, and a `label`.

### 2. Data Exploration
- The structure, sample rows, and label distribution are examined.
- Provides insight into class balance (normal vs. anomalies).

### 3. Preprocessing
- The dataset is split into features (`X`) and labels (`y`).
- A standard **train-test split** (typically 70% train, 30% test) is performed.
- **Feature scaling** (standardization) is used to normalize input features for the SVM.

### 4. SVM Model Training
- An SVM classifier (`sklearn.svm.SVC`) with RBF (radial basis function) kernel is trained.
- The RBF kernel helps the SVM find nonlinear boundaries, which is crucial for anomaly detection in complex data.

### 5. Prediction & Evaluation
- The trained model predicts labels on the test set.
- Evaluation metrics printed:
  - **Accuracy**
  - **Confusion Matrix**
  - **Classification Report** (precision, recall, F1-score)

#### Typical Confusion Matrix Interpretation:
- True Negatives (e.g., 1503): Normal traffic correctly classified.
- False Positives (0): Normal traffic misclassified as anomaly.
- False Negatives (12): Anomalies missed (classified as normal).
- True Positives (30): Anomalies correctly detected.

### 6. Visualization
- Confusion matrix plotted as a heatmap for performance clarity.
- (Advanced) 2D PCA projection and SVM decision boundary visualizations show class separability.

## Key Libraries Used

- `pandas` & `numpy`: Data manipulation
- `scikit-learn`: SVM, metrics, preprocessing, splitting, PCA
- `matplotlib` & `seaborn`: Plotting

## Usage

- **Jupyter Notebook**: Step through the analysis interactively.
- **Python Script**: Run the pipeline end-to-end for automation (`python training_svm_model_for_normal_and_anomalies_traffic.py`).

---

**Results example:**  
- Accuracy: ~99%
- Very high detection for normal traffic, strong identification of anomalies.

---

## Credits

Developed by [ikramkakar](https://github.com/ikramkakar).  
Dataset: included or see `Network_traffic.csv`.

## License

MIT License (or specify your own).
