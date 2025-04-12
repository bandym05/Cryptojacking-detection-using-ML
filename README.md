# 🔒 Cryptojacking Detection using Machine Learning

Welcome to the Cryptojacking Detection Challenge solution developed for the UmojaHack Africa 2023 competition!

This project leverages machine learning techniques to classify network activity as either **cryptojacking** or **normal** behavior based on host-based and network-based features.

## 🧠 What is Cryptojacking?

Cryptojacking is a type of cyberattack in which malicious scripts hijack computing resources to mine cryptocurrency without the user's consent or knowledge. This leads to reduced system performance, crashes, and increased energy consumption.

## 🎯 Objective

Build a binary classification model that can effectively detect cryptojacking activity using various system and network performance metrics.

---

## 📁 Dataset Overview

The dataset contains the following files:

- `Train.csv` – contains the training data with labeled instances.
- `Test.csv` – contains the unlabeled data for predictions.
- `SampleSubmission.csv` – format to submit predictions.

Each row in the dataset represents a snapshot of network activity and includes features like:

- I/O operations and bytes
- Processor time
- Disk read/write speeds
- Network bytes sent/received
- Page errors, etc.

---

## 🧪 Workflow

### 1. **Importing Libraries**

Essential libraries used include:
- `pandas`, `numpy` for data handling
- `matplotlib`, `seaborn` for visualization
- `sklearn` for machine learning and evaluation
- `imblearn` for handling class imbalance

### 2. **Exploratory Data Analysis**
- Statistical summaries
- Missing values & duplicates check
- Target label distribution
- Correlation heatmap

### 3. **Data Preprocessing**
- Standardization using `StandardScaler`
- Splitting the dataset into training and validation sets
- Addressing class imbalance using `SMOTETomek`

### 4. **Modeling**

Several models were tested (Logistic Regression, Decision Trees, SVM), but the best performance was achieved using:

✅ **Random Forest Classifier**

```python
from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier()
model.fit(X_train, y_train['Label'])
```

### 5. **Evaluation**

```bash
Accuracy: 94%
F1-Score for Class 1 (cryptojacking): 0.89
```

### 6. **Submission**
- Predictions were made on the test set
- Results saved in `UHA_23_crypto.csv`

---

## 🗃️ File Structure

```
.
├── Train.csv
├── Test.csv
├── SampleSubmission.csv
├── cryptojacking_detection.ipynb
├── UHA_23_crypto.csv
└── README.md
```

---

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/cryptojacking-detection-ml.git
   cd cryptojacking-detection-ml
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook cryptojacking_detection.ipynb
   ```

---

## 📊 Results

| Metric      | Score |
|-------------|-------|
| Accuracy    | 94%   |
| Precision   | 91%   |
| Recall      | 87%   |
| F1-Score    | 89%   |

---

## 📌 Notes

- No missing values or duplicates were found.
- Dataset was slightly imbalanced, handled with SMOTETomek.
- Random Forest provided the best balance between precision and recall.

---

## 👨‍💻 Author

**Bandile Malaza**  
Managing Partner @ Swazigist (Pty) Ltd  
🌍 Eswatini

---

## 🏁 License

This project is open-source and available under the [MIT License](LICENSE).
