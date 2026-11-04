# FlatSight - HDB Resale Price Estimator

Agile MLOps pipeline and baseline models for predicting Singapore HDB resale prices using `scikit-learn`.

---

## 🛠️ Prerequisites & Setup

### 1. Clone the Repository
Ensure you have set up SSH in GitHub before cloning:
```bash
git clone git@github.com:EthanNgoh07/FlatSight-EthanNgoh.git
cd FlatSight-EthanNgoh
```

### 2. Python Virtual Environment Setup
Make sure you are using Python 3.10 or later.

#### **Windows (PowerShell)**
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```
*Note: If PowerShell blocks script activation, run `.venv\Scripts\activate.bat` in Command Prompt.*

#### **macOS / Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

---

## 📊 Dataset Setup

1. Obtain the official class HDB resale price CSV dataset from brightspace.
2. Place the CSV file in the local data directory:
   ```text
   data/raw/hdb_resale_prices.csv
   ```
   *(Create the `data/raw/` directory locally if it does not exist).*

> ⚠️ **Important:** Raw dataset CSVs, local data folders (`data/raw/`, `data/processed/`), model artifacts (`*.pkl`, `*.joblib`), and virtual environments (`.venv/`) are listed in `.gitignore` and must **NEVER** be committed to Git.

---

## 🚀 Running Model Training

All models share common feature engineering and data splitting definitions in `src/features.py`. 

Always execute scripts **from the repository root** using Python's module flag (`-m`) to ensure local imports resolve correctly.

### **Linear Regression (Member 1 / Scrum Master)**
```bash
python -m src.models.linear_model
```

### **Random Forest (Member 2)**
```bash
python -m src.models.rf_model
```

### **Gradient Boosting (Member 3)**
```bash
python -m src.models.gb_model
```

*(Note: For 4-member teams, Ridge Regression is available via `python -m src.models.ridge_model`)*

---

## 🌲 Git Branching & Workflow Rules

1. **Only project initial setup goes directly to `main`.**
2. Every feature or model improvement requires a dedicated feature branch created from an updated `main`:
   - `feat/model-linear`
   - `feat/model-random-forest`
   - `feat/model-boost`
3. Commit messages must follow conventional commit naming and link to an open issue:
   - Example: `feat: train random forest and report metrics #12`
4. Open a Pull Request (PR) targeting `main`, request peer review from a teammate, and ensure code is validated prior to merging.
