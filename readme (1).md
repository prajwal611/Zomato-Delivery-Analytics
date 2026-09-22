# ⚡ Quick-Commerce Delivery Latency & SLA Diagnostic Engine

An end-to-end data analytics project examining fulfillment bottlenecks, order preparation delays, and delivery SLA breaches across high-density quick-commerce urban zones.

---

## 📌 Project Overview

Quick-Commerce (Q-Commerce) platforms rely heavily on 10-to-15-minute delivery SLAs to maintain customer retention. However, adverse weather, peak traffic windows, and dark store prep bottlenecks frequently lead to SLA breaches and operational revenue loss.

This project analyzes **20,000+ delivery logs** across multiple dark store catchment zones to pinpoint root causes of fulfillment latency and propose data-backed operational adjustments.

### Key Objectives
* **Isolate Bottlenecks:** Differentiate between **Dark Store Prep Delays** (order packing) vs. **Transit Delays** (road conditions/rider supply).
* **Quantify Weather & Traffic Impacts:** Measure the exact tipping points where rain and peak traffic lead to exponential SLA failure rates.
* **Propose Operational Fixes:** Model targeted service-radius adjustments to safeguard fulfillment reliability without sacrificing order volume.

---

## 🔑 Key Findings & Business Insights

1. **Dark Store Prep Time Spike:** 38% of late deliveries were triggered before the rider left the dark store, caused by a dispatch lag during 7:00 PM – 9:00 PM peak ordering windows.
2. **Weather Tipping Point:** Light rainfall (<5mm) had negligible impact on delivery times, whereas precipitation exceeding 10mm triggered a **3.2x increase in SLA breach probability** due to severe rider shortages.
3. **Speed vs. Rating Myth:** Higher-rated riders (4.5–5.0) do not travel significantly faster in transit; rather, their top ratings strongly correlate with lower prep-phase delays and higher fulfillment consistency.
4. **Actionable Recommendation:** Throttling dark store service radii from 2.0 km down to 1.3 km during severe rain events reduces SLA breach risk by **18%** while protecting core neighborhood order fulfillment.

---

## 🛠️ Data Pipeline & Methodology

```
[Raw Order Logs] ──► [Data Cleaning & Outlier Removal] ──► [Feature Engineering] ──► [Exploratory Analysis & Visualizations]
```

* **Data Cleaning:** Filtered out erroneous speed records (>60 km/h city driving anomalies), handled missing timestamps, and normalized SLA flags.
* **Feature Engineering:** Calculated explicit `prep_time_min`, derived `transit_time_min`, computed Haversine distances, and categorized rider ratings into analytical tiers.
* **Exploratory Data Analysis:** Conducted bi-variate distributions, SLA breach rate pivot tables, and correlation heatmaps using Pandas and Seaborn.

---

## 📂 Project Structure

```text
├── data/
│   └── delivery_orders.csv      # Raw order logs dataset
├── notebooks/
│   └── qcommerce_sla_analysis.ipynb  # Interactive Jupyter Notebook with full EDA
├── scripts/
│   └── qcommerce_sla_analysis.py    # Cleaned, modular Python pipeline
├── outputs/
│   └── sla_breach_matrix.png   # Exported heatmap and distribution charts
├── requirements.txt            # Python dependencies
└── README.md                   # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites
Make sure you have **Python 3.8+** installed on your system.

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/qcommerce-sla-analysis.git
   cd qcommerce-sla-analysis
   ```

2. **Create a virtual environment (Optional but Recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Notebook or Python Script:**
   ```bash
   jupyter notebook notebooks/qcommerce_sla_analysis.ipynb
   ```
   *OR*
   ```bash
   python scripts/qcommerce_sla_analysis.py
   ```

---

## 📊 Sample Visualizations

* **SLA Breach Matrix:** Evaluates the interaction between weather severity and traffic density against customer order delay rates.
* **Prep Latency Analysis:** Identifies dark store fulfillment bottlenecks across different operating hours.

---

## 🧰 Tech Stack & Tools

* **Language:** Python 3.11
* **Data Processing:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Environment:** Jupyter Notebook / VS Code