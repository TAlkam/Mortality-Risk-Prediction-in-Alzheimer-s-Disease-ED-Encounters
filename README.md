# Mortality-Risk Prediction in Alzheimer’s Disease ED Encounters  
**National Emergency Department Sample (NEDS 2012-2014)**  

This repository reproduces all analyses and figures reported in the manuscript submitted to the **_Journal of Alzheimer’s Disease_** (JAD):

> “Flagging High-Risk Comorbidities in Alzheimer’s Emergency Department Visits: A Machine Learning Analysis of Mortality Outcomes
”

The code trains four classifiers, selects the best model on an internal validation split, re-fits it on 80 % of the data, and reports final metrics on an untouched 20 % test set.  All steps—including SHAP interpretability—can be rerun end-to-end in **< 5 minutes** on a free Colab CPU.

---

## Repository layout

| Path | Purpose |
|------|---------|
| `pipeline.ipynb` | **Primary, executable notebook** (train → validate → test → SHAP) |
| `pipeline.py` | Script version—same logic, no notebook overhead |
| `figures/` | SHAP plots and ROC curves used in the manuscript |
| `requirements.txt` | Exact package versions (Python ≥ 3.10, scikit-learn 1.5.0, XGBoost 2.0.0, SHAP 0.45.0, …) |
| `README.md` | You are here |

> **Note ⟶ HCUP licence**  
> The raw NEDS data are *not* redistributed here; obtain them directly from HCUP and place the `.dta` file in the working directory before execution.

---

## Quick start (Colab or Jupyter)

```bash
# clone and enter
git clone https://github.com/YourHandle/AD_ED_Mortality.git
cd AD_ED_Mortality

# create environment (optional but recommended)
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
