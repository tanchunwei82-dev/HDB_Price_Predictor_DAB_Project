# 🏘️ WOW! HDB Resale Price Predictor

> **The Model Citizens** · Data Analytics Bootcamp Part-Time · General Assembly Singapore

A data-backed Streamlit web app that helps **WOW! Real Estate** agents estimate HDB resale prices in Singapore using three ML models — Linear Regression, Random Forest, and XGBoost — along with live comparable transaction analysis.

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://your-app-name.streamlit.app)

---

## 📌 Project Overview

Singapore's HDB resale market is dynamic and location-sensitive. This tool gives agents an instant, data-backed valuation for any flat by combining:

- **Model Comparison** — side-by-side evaluation of Linear Regression, Random Forest, and XGBoost
- **Interactive Feature Selection** — toggle which features to include and see metrics update live
- **Live Prediction** — enter any flat's details and receive an instant price estimate
- **Comparable Transactions** — see real historical transactions from similar flats in the same town

---

## 📊 Dataset

| Dataset | Records | Description | Download |
|---|---|---|---|
| `train_clean_working.csv` | ~160,000 | Cleaned HDB resale transactions (train set) | [Google Drive](https://drive.google.com/file/d/1J2LjbZJ2C2PSZLblhxa9xUrAg0fDeO7v/view?usp=sharing) |
| `test_clean_working.csv` | ~16,000 | Cleaned HDB resale transactions (test set) | [Google Drive](https://drive.google.com/file/d/1rljS-VYRuBVXpO1mm40J1URiIm0X6Hin/view?usp=sharing) |

> **Note:** The CSVs are not committed to the repo. Download both files from the links above and place them in the project root (alongside the notebooks) so `data_cleaning_eda.ipynb` and `ml.ipynb` can locate them.

**Key Features Used:**

| Feature | Description |
|---|---|
| `flat_type_encoded` | Flat type (1–5 Room, Executive, etc.) |
| `town_encoded` | HDB town (label-encoded) |
| `hdb_age` | Age of the block in years |
| `mid` | Storey mid-level |
| `mrt_nearest_distance` | Distance to nearest MRT (m) |
| `pri_sch_nearest_distance` | Distance to nearest primary school (m) |
| `hawker_within_1km` | No. of hawker centres within 1 km |
| `mall_within_1km` | No. of malls within 1 km |
| `bus_stop_nearest_distance` | Distance to nearest bus stop (m) |

---

## 🗂️ Repository Structure

```
2_model_citizen_project_3/
│
├── src/                          # Streamlit app & model files
│   ├── app.py                    # Main app (all 4 tabs)
│   ├── app_prediction.py         # Prediction tab only
│   ├── app_evaluation.py         # Evaluation tabs only
│   ├── model.pkl                 # Trained XGBoost model
│
├── data_cleaning_eda.ipynb       # Data cleaning & EDA notebook
├── ml.ipynb                      # Model training notebook
├── eda.twbx                      # Tableau workbook
├── slides.pdf                    # Project presentation
│
├── requirements.txt              # Python dependencies
├── .gitignore                    # Files excluded from Git
├── .streamlit/
│   └── config.toml               # Streamlit theme & server config
└── README.md                     # This file
```

---

## 🚀 Running Locally

### Prerequisites
- Python 3.10 or higher
- pip

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME

# 2. Install dependencies
pip install -r requirements.txt

# 3. Navigate into src and run the app
cd src
python -m streamlit run app.py
```

The app will open at `http://localhost:8501`.

> **Tip:** You can also run individual modules:
> ```bash
> python -m streamlit run app_prediction.py   # Prediction tab only
> python -m streamlit run app_evaluation.py   # Evaluation tabs only
> ```

---

## 🧠 Models

| Model | Train R² | Notes |
|---|---|---|
| Linear Regression | ~0.80 | Baseline; fast, interpretable |
| Random Forest | ~0.97 | Ensemble; feature importance included |
| **XGBoost** | **~0.98** | Best performer; used for live prediction |

The saved `model.pkl` is the pre-trained XGBoost model used in the **Live Prediction** tab.

---

## 👥 Team

**The Model Citizens** — General Assembly Data Analytics Bootcamp, Part-Time Cohort 2026

---

## 📄 License

This project is for educational purposes. Data sourced from HDB Singapore public resale records.
