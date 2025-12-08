# **Insurance Risk Analytics Project (ACIS)**

## **Project Overview**

This project analyzes historical insurance policy and claims data for ACIS to identify low-risk segments and optimize marketing and premium strategies. The analysis involves:

* Exploratory Data Analysis (EDA) to understand the dataset.
* Outlier detection and feature engineering.
* Data version control using DVC for reproducibility.
* Preparation for hypothesis testing and predictive modeling.

---

## **Project Structure*

```
ACIS-Insurance-Analytics/
│
├─ data/
│   ├─ raw/                  # Raw datasets (tracked with DVC)
│   ├─ processed/            # Cleaned and processed datasets
│
├─ notebooks/
│   ├─ 01_EDA.ipynb          # Exploratory Data Analysis notebook
│   ├─ 02_DataPrep_DVC.ipynb # DVC integration and data prep
│
├─ scripts/
│   ├─ data_cleaning.py      # Data cleaning and feature engineering scripts
│
├─ dvc.yaml                  # DVC pipeline file
├─ .gitignore
├─ README.md
└─ requirements.txt
```

---

## **Setup Instructions**

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/ACIS-Insurance-Analytics.git
cd ACIS-Insurance-Analytics
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

3. **Initialize DVC and pull raw datasets**

```bash
dvc pull
```

*Note:* The raw dataset `claimdata.txt` is tracked with DVC to ensure version control.

---

## **Data Overview**

**Key columns:**

* `TotalPremium`, `TotalClaims` – Premium and claim amounts.
* `CustomValueEstimate` – Estimated value of insured items.
* `VehicleType`, `RegistrationYear`, `Province`, `Bank` – Key categorical attributes.
* `LossRatio`, `HasClaim`, `Margin` – Derived features for analysis.

**Missing Values Summary:**

* Columns with >5% missing values include `NumberOfVehiclesInFleet`, `CrossBorder`, `CustomValueEstimate`, `Rebuilt`, `Converted`, `WrittenOff`, `NewVehicle`, `Bank`.

**Outlier Analysis:**

* `TotalPremium`: 20.9% outliers
* `TotalClaims`: 0.28% outliers
* `CustomValueEstimate`: 0.81% outliers

Outliers were capped for analysis and visualization.

---

## **EDA Summary**

* Distribution of `TotalPremium` and `TotalClaims` shows skewness.
* Loss ratio varies by province and vehicle type.
* Weak correlation observed between `TotalPremium` and `CustomValueEstimate`.
* Strong correlation between `TotalClaims` and `LossRatio` (expected).

**Key Plots:**

1. Histogram of premiums and claims
2. Loss ratio by province (boxplot)
3. Scatter plot: CustomValueEstimate vs TotalPremium

---

## **Data Version Control (DVC)**

* DVC initialized: `dvc init`
* Raw dataset tracked: `dvc add data/raw/claimdata.txt`
* Dataset pushed to remote storage: `dvc push`

This ensures reproducibility and easy dataset management across collaborators.

---

## **Next Steps**

1. **Task 3 – Hypothesis Testing**: Segment data and test risk differences.
2. **Task 4 – Predictive Modeling**: Train models to predict claims and optimize premiums.
3. Continuous documentation of all workflows for reproducibility.

---

## **Tools and Libraries**

* Python: Pandas, NumPy, Matplotlib, Seaborn, SciPy
* Version Control: Git, GitHub
* Data Versioning: DVC

---

This README reflects **interim progress**, covering Tasks 1 (EDA) and 2 (DVC integration), and provides a roadmap for the remaining work.