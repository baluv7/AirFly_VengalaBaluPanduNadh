# ✈️ AirFly Insights: Airline Performance & Operations Analysis

**AirFly Insights** is an end-to-end data analytics project focused on studying flight delays, cancellations, and route behavior. By processing raw aviation data with **Python** and visualizing it in **Microsoft Power BI**, this project transforms complex operational logs into interactive dashboards that support decision-making for airline stakeholders.

---

## 📌 Project Statement

The goal of this project is to analyze large-scale airline flight data to uncover operational trends, delay patterns, cancellation behavior, and route efficiency.

**Key Questions Addressed:**
* What causes flight delays?
* Which airports experience the most cancellations?
* How do delays vary by hour, distance, season, and airline?
* Which routes perform efficiently and which require improvement?

---

## 💾 Dataset

* **Source:** Kaggle Airlines Flights Data
* **Scale:** 60M+ rows (sampled for dashboarding)
* **Key Attributes:**
  * Airline, Origin & Destination Airports
  * Scheduled vs. Actual Departure/Arrival
  * Delay Minutes & Reasons
  * Cancellation & Diverted Flags
  * Distance & Route

**Files:**
* `New_flight_delays.csv` — Raw dataset
* `cleaned_flight_delays.csv` — Intermediate cleaned dataset
* `final_flight_delays_for_dashboard.csv` — Final processed dataset used in Power BI

---

## 🛠️ Data Processing Workflow

All cleaning and feature engineering were performed in **Python** using Pandas and NumPy (`AirFly_Insight.ipynb`).

### 1. Data Cleaning
* **Imputation:** Filled missing `DelayReason` with "Not Delay" and `DelayMinutes` with 0.
* **Formatting:** Converted datetime columns using `pd.to_datetime()`.
* **Sanitization:** Removed duplicate rows and extreme delays (> 300 minutes).

### 2. Outlier Handling
* Applied **Interquartile Range (IQR)** capping for numeric columns.
* Replaced values falling outside the `Q1 – 1.5×IQR` and `Q3 + 1.5×IQR` range.

### 3. Feature Engineering
Generated new fields to enhance drill-down capabilities:
* **Time Features:** Year, Month, Day, Hour, Minute, Day of Week, Season.
* **Route Feature:** Created "Origin-Destination" string (e.g., *ATL-JFK*).
* **Encoding:** Applied label encoding to the `Airline` column.
* **Aggregations:** Calculated monthly average delays, average distances, and total cancellations.

### 4. Exploratory Data Analysis (EDA)
Performed using **Matplotlib** and **Seaborn**:
* Delay distribution histograms.
* Cancellation count bar plots.
* Delay vs. Distance scatter plots.
* Correlation heatmaps and box plots for outlier detection.

---

## 📊 Power BI Dashboards

The project includes four dashboards (`AIRFLY_INSIGHT.pbix`), each targeting a specific operational area.

### 1. Overview & Operational Metrics
* **Purpose:** High-level fleet performance summary.
* **Key Visuals:** Average Delay (~10 mins), Total Cancellations (~1.75M).
* **Insights:** Delay reasons (Weather, Maintenance, ATC) are distributed evenly. **Southwest** and **Delta** contribute the highest total delay minutes.

### 2. Delay Analysis & Performance
* **Purpose:** Time-based delay behavior.
* **Insights:** Delays **peak during afternoon hours**. Each delay reason category contributes roughly ~33% to the total.

### 3. Route & Airport Exploration
* **Purpose:** Geographical efficiency analysis.
* **Insights:** Distance does **not** strongly correlate with delay time. High-volume routes include **ORD-JFK**, **ATL-MIA**, and **DFW-SEA**.

### 4. Cancellation Insights & Trends
* **Purpose:** Identifying cancellation hotspots.
* **Insights:**
  * **Top Cancellation Hubs:** Chicago (ORD ~350K) and Atlanta (ATL ~349K).
  * LAX, JFK, and DFW follow closely.
  * The "Not Delay" category often indicates operational/scheduling cancellations.

---

## 🚀 Key Results & Conclusions

* **Average Delay Time:** ~10 minutes
* **Total Cancellations:** ~1.75 million
* **Primary Disruption Factors:** Weather and Air Traffic Control.
* **Critical Hubs:** Chicago (ORD) and Atlanta (ATL) are the most prone to cancellations.
* **Temporal Patterns:** Peak delays consistently occur in the **afternoon and evening**.

---

## 💻 Technologies Used

* **Language:** Python 🐍 (Pandas, NumPy, Scikit-learn)
* **Visualization:** Matplotlib, Seaborn (EDA)
* **Business Intelligence:** Microsoft Power BI 📊
* **Environment:** Jupyter Notebook / Google Colab

---

## 📂 Repository Contents

| File Name | Description |
| :--- | :--- |
| `AirFly_Insight.ipynb` | Full code for data cleaning, preprocessing, and feature engineering. |
| `AIRFLY_INSIGHT.pbix` | The interactive Power BI dashboard file. |
| `final_flight_delays_for_dashboard.csv` | Cleaned dataset used for the dashboards. |
| `Airfly_Insight01-04.png` | Screenshots of the dashboards. |

---

## 🔗 Links

* **GitHub Repository:** [https://github.com/baluv7/AirFly_VengalaBaluPanduNadh](https://github.com/baluv7/AirFly_VengalaBaluPanduNadh)
