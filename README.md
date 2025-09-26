# IPO Delisting Prediction

This project predicts whether an IPO company will be **delisted within the next five quarters** based on financial statement data retrieve by https://github.com/ZixinIsabelDeng/selenium-web-scraping-tool-.  
It is built on my original GitHub research project [Predicting-the-Delisting-of-an-IPO-Company-Within-the-Next-Five-Quarters](https://github.com/ZixinIsabelDeng/Predicting-the-Delisting-of-an-IPO-Company-Within-the-Next-Five-Quarters)  
and expanded into a modular, config-driven workflow with Jupyter notebooks.

In this version, the workflow is designed to be **Databricks-ready**:
- Notebooks are structured to run seamlessly inside **Databricks Notebook Workflows**.  
- **MLflow integration** is included for experiment tracking and reproducibility.  
- Config files (`feature_config.yaml`, `model_config.yaml`) make it easy to parameterize experiments when running at scale.  
- Data pipelines (ingestion → feature engineering → model training) can be orchestrated either locally or directly on a Databricks cluster.  

This setup allows the same project to run **locally for prototyping** or **on Databricks for scalable distributed training**.


---

## 📂 Project Structure

```
IPO_Delisting_Prediction/
│── data/                   # Raw and processed datasets
│   ├── raw/                # Original input data
│   ├── processed/          # Cleaned & feature-engineered data
│
│── notebooks/              # End-to-end workflow in notebooks
│   ├── 01_data_ingestion.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_exploratory_analysis.ipynb
│   ├── 04_model_training.ipynb
│   ├── 05_model_evaluation.ipynb
│   └── 06_model_deployment.ipynb
│
│── configs/                # Config files
│   ├── feature_config.yaml
│   └── model_config.yaml
│
│── requirements.txt        # Python dependencies
│── README.md               # Project documentation
```

---

## ⚙️ Setup Instructions

1. **Clone the repo**
   ```bash
   git clone https://github.com/<your-username>/IPO_Delisting_Prediction.git
   cd IPO_Delisting_Prediction
   ```

2. **Create a virtual environment (Python 3.11 recommended)**
   ```bash
   python3.11 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Register Jupyter kernel**
   ```bash
   python -m ipykernel install --user --name=ipo_env --display-name "Python (ipo_env)"
   ```

---

## 🚀 Workflow

1. **Data Ingestion** → Load raw IPO financial data.  
2. **Feature Engineering** → Create ratios like leverage, profit margin, and cashflow ratios.  
3. **Exploratory Analysis** → Visualize data and understand distributions.  
4. **Model Training** → Train ML models (Logistic Regression, Random Forest, etc.).  
5. **Model Evaluation** → Measure accuracy, ROC-AUC, and other metrics.  
6. **Model Deployment** → Save and register models for future use.

---

## 🛠️ Config Files

- **`feature_config.yaml`** → Defines which features to engineer and include.  
- **`model_config.yaml`** → Stores model hyperparameters and training settings.  

This makes the pipeline flexible and easily adjustable.

---

## 📊 Tech Stack

- Python 3.11  
- pandas, numpy (data handling)  
- matplotlib, seaborn (visualization)  
- scikit-learn (machine learning)  
- MLflow (experiment tracking, optional)  
- Databricks (optional, for scaling workflows)  

---

## 📈 Example

- **Input:** Quarterly balance sheet + income statement data for IPO firms.  
- **Output:** Binary classification → `Delisted: Yes / No` within five quarters.  

---

## 👤 Author

Developed by **Zixin (Isabel) Deng**.  
Feedback and contributions are welcome! 🚀

