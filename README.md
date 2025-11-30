# **📈 InterestRatePred — Lending Club Interest Rate Prediction**

A complete end-to-end interest rate prediction pipeline built using the Lending Club dataset.
This repository includes:

✔ Automated Kaggle dataset download
✔ Extensive EDA (statistical, visual, geospatial)
✔ Full data cleaning, preprocessing & leakage-prevention
✔ Missing value treatment with domain-justified logic
✔ Feature engineering (dates, employment, credit history length, one-hot encoding)
✔ Train/test split + scaling
✔ Linear Regression baseline model
✔ Evaluation metrics + visualizations

This project demonstrates **true industry-grade data cleaning**, **feature engineering**, and **model evaluation** on one of the most complex open financial datasets available.

---

## **📌 Project Structure**

```
├── interestratepred.py            # Full cleaned pipeline exported from Colab
├── interestratepred.ipynb         # Jupyter notebook
├── README.md                      # Documentation
```

---

## **🚀 Features**

### **1. Automated Dataset Handling**

* Downloads the Lending Club dataset directly via Kaggle API.
* Creates appropriate folder structures in Google Drive or local runtime.

### **2. Exploratory Data Analysis (EDA)**

* Column-wise type analysis
* Missing value analysis
* Histograms & scatter plots
* Boxplots (Grade / Sub-grade vs Interest Rate)
* Loan purpose distribution
* U.S. state-wise choropleth of average interest rate

### **3. Intelligent Feature Dropping**

The model removes columns based on:

* **Data leakage** (post-loan features like total_pymnt, recoveries, etc.)
* **Irrelevant rare-use columns** (hardship, secondary applicant data)
* **Redundant identifiers** (id, member_id, url, desc)

Each decision includes domain-based justification.

### **4. Missing Value Imputation**

Handled with purpose-built strategies:

* **0** for “no event occurred” types
* **Median** for util/financial numeric columns
* **Mode** for categoricals
* **Extreme values** for “long ago” missing timestamps
* **Datetime parsing** with sanity corrections

### **5. Feature Engineering**

* Clean `int_rate` → numeric
* Convert `term` to integers
* `emp_length` → ordinal numeric encoding
* Credit history length (in days)
* One-hot encoding with `drop_first=True`

### **6. Train-Test Split + Scaling**

* 80/20 train/test
* StandardScaler for robust normalization
* Zero-variance feature removal

### **7. Baseline Model**

**Linear Regression**

* Fitted on fully preprocessed data
* Evaluated on R², MAE, RMSE

Visualizations include:

* Actual vs Predicted
* Residuals
* Top feature correlations

---

## **📊 Model Performance Example**

(Example numbers — replace with your actual result)

| Metric        | Value |
| ------------- | ----- |
| R²            | 0.82  |
| MAE           | 1.94  |
| RMSE          | 2.41  |
| Training Time | 0.32s |

---

## **🧠 Key Technical Concepts Demonstrated**

* Data leakage prevention
* Correlation exploration
* Proper handling of high-cardinality categorical variables
* Robust preprocessing design
* Regression evaluation techniques
* End-to-end reproducible ML pipeline

---

## **🛠 Technologies Used**

* Python
* Pandas
* NumPy
* Scikit-learn
* Seaborn / Matplotlib
* Plotly
* Kaggle API
* Google Colab

---

## **📂 How to Run**

### **1. Clone repo**

```bash
git clone https://github.com/your-username/InterestRatePred
cd InterestRatePred
```

### **2. Add your `kaggle.json`**

Upload it into your runtime or local `.kaggle` folder.

### **3. Install dependencies**

```bash
pip install -r requirements.txt
```

### **4. Run the script**

```bash
python interestratepred.py
```

---

## **📌 Future Improvements**

* Add Random Forest, XGBoost, GradientBoosting models
* Model comparison dashboard
* Save best model using joblib
* Cloud deployment (FastAPI + Docker)
* Interactive Notebook version

---

## **📜 License**

MIT License
