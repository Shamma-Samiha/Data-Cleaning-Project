# 🧼 Data Cleaning Project — Crime & Incarceration (USA, 2001–2016)

A hands-on notebook demonstrating **missing value diagnosis and treatment** on a multi-state crime & incarceration dataset.
It compares several imputation strategies side-by-side and reports the **remaining missingness** after each approach.

## 📦 Dataset
Rows contain U.S. states (plus Federal) by year with crime totals and categories.

**Example columns**
- `jurisdiction`, `includes_jails`, `year`, `prisoner_count`
- `state_population`, `violent_crime_total`, `property_crime_total`
- `murder_manslaughter`, `rape_legacy`, `rape_revised`, `robbery`, `agg_assault`
- `burglary`, `larceny`, `vehicle_theft`
- (Dropped later) `Unnamed: 17`

Time span in the sample: **2001–2016**.

## 🎯 Objectives
1. Audit missingness by column.
2. Apply multiple strategies: **mean**, **median**, **mode**, **forward-fill**, **backward-fill**.
3. **Compare** “before vs after” missing counts for each strategy.
4. Document trade-offs and good practices for reproducible cleaning.


````

## ⚙️ Environment
- **Python** 3.10+
- **Jupyter / Google Colab**
- **pandas**, **numpy**

Install (local):
```bash
pip install pandas numpy jupyter
````

## 🚀 Run

Open the notebook:

* **Colab:** Click the “Open in Colab” badge in the first cell.
* **Local:** `jupyter notebook Crime_Data_Missing_Value_Handling.ipynb`

Ensure `data/crime_and_incarceration.csv` is available.

## 🔎 Missingness Audit

The notebook prints a count of `NaN`s per column (e.g., population, violent crime totals, etc.) and highlights fully empty/extraneous columns such as **`Unnamed: 17`**.

## 🧠 Methods Implemented

* **Mean imputation** (numeric stability)
* **Median imputation** (robust to outliers)
* **Mode imputation** (categorical/skewed)
* **Forward fill** (`ffill`) and **Backward fill** (`bfill`) for time-like continuity

## 📈 Results Snapshot

* Mean/Median: remove most numeric `NaN`s; categorical flags may remain.
* Mode: clears many categorical gaps.
* FFill/BFill: good for time series continuity but may propagate errors if there are long initial/final gaps.
* `Unnamed: 17`: safe to **drop** (entirely missing).

## 📝 License

MIT

```
