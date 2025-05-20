# 💳 Fraud Detection Using K-Means Clustering

This project applies **unsupervised machine learning (K-Means clustering)** to detect **potentially fraudulent financial transactions** without using labeled data.

---

## 📁 Dataset

- **Source:** [Kaggle - Fraud Detection in Financial Transactions](https://www.kaggle.com/datasets/rohit265/fraud-detection-dynamics-financial-transaction)
- **Data Points:** Over 6 million transactions
- **Columns Used:**
  - `type`: Transaction type (e.g., TRANSFER, CASH_OUT)
  - `amount`, `oldbalanceOrg`, `newbalanceOrig`, `oldbalanceDest`, `newbalanceDest`
  - `isFraud`: Indicates if a transaction is fraudulent (used for evaluation only)

---

## ⚙️ Project Workflow

### 1. **Data Preprocessing**
- Dropped irrelevant columns (`nameOrig`, `nameDest`, `isFlaggedFraud`)
- Handled missing values (if any)
- Converted categorical column `type` using One-Hot Encoding
- Created additional behavioral features:
  - `balance_diff`
  - `dest_balance_change`
  - `sent_more_than_available`

### 2. **Feature Scaling**
- Used `StandardScaler` to normalize numerical values before clustering

### 3. **K-Means Clustering**
- Applied `KMeans(n_clusters=6)`
- Grouped similar transactions based on their behavior

### 4. **Dimensionality Reduction**
- Used **PCA (Principal Component Analysis)** to reduce data to 2D
- Visualized clusters using seaborn scatterplots

### 5. **Evaluation**
- Analyzed average fraud rate in each cluster
- Identified clusters with high concentration of frauds
- Verified patterns using boxplots and fraud distribution graphs

---

## 📊 Key Results

- Certain clusters had a **much higher fraud rate**, showing K-Means could detect suspicious patterns
- Fraudulent transactions often involved:
  - Sending more than the available balance
  - Sudden large changes in account balances
- Clustering helped uncover **anomalous transaction behavior**

---

## 🚀 Applications

- **Banks & Digital Wallets**: Monitor and pre-screen transactions
- **Real-Time Systems**: Flag outlier clusters for deeper investigation
- **Risk & Compliance**: Investigate clusters prone to fraud

---

## 🔮 Future Work

- Combine clustering with supervised learning (semi-supervised)
- Tune the number of clusters and features
- Try advanced clustering (DBSCAN, Isolation Forest)

---

## 📦 Requirements

Install dependencies via pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
