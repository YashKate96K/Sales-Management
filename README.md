# 📊 Sales Data Analysis & Executive Insights

A comprehensive exploratory data analysis (EDA) project evaluating annual e-commerce sales performance across seasonality, geographic markets, advertisement timing, product affinity, and price elasticity[cite: 1, 2].

---

## 🚀 Project Overview
This project consolidates 12 individual monthly sales datasets into a centralized data pipeline to uncover key revenue drivers, customer purchasing patterns, and actionable business strategies[cite: 1, 2].

---

## 💡 Key Business Insights

### 1. Best Month for Sales (Seasonality)
- **Top Month:** **December** was the highest-grossing month, generating **~$4.61M** in revenue with **28,114** items sold[cite: 1, 2].
- **Peak Surge:** Strong upward momentum throughout Q4, with **October** ($3.74M) and **December** peaking sharply due to holiday shopping and promotional discounts[cite: 1, 2].
- **Low Season:** **January** (~$1.82M) and **September** (~$2.10M) recorded the lowest sales volume, indicating a post-holiday spending drop[cite: 1, 2].

### 2. Geographic Performance (City-by-City)
- **Top Market:** **San Francisco (CA)** led all regions, generating **$8.26M** across **50,239** items sold[cite: 1, 2].
- **Key Secondary Markets:**
  - **Los Angeles (CA):** $5.45M (33,289 items)[cite: 1, 2]
  - **New York City (NY):** $4.66M (27,932 items)[cite: 1, 2]
  - **Boston (MA):** $3.66M (22,528 items)[cite: 1, 2]
- **Lowest Revenue:** **Portland (ME)** recorded the lowest sales at **~$449.8K**[cite: 1, 2].
- **Takeaway:** Over 60% of total revenue is concentrated in West Coast tech hubs (California), indicating localized inventory and targeted marketing should be prioritized there[cite: 2].

### 3. Optimal Advertisement Timing
- **Daily Peak Hours:** Order volume exhibits two distinct daily spikes:
  - **Midday Peak:** **11:00 AM – 1:00 PM** (lunchtime browsing)[cite: 1, 2].
  - **Evening Peak:** **7:00 PM – 8:00 PM** (post-work relaxation)[cite: 1, 2].
- **Recommendation:** Schedule push notifications, digital ad campaigns, and promotional email blasts slightly before peak periods—specifically at **10:30 AM** and **6:30 PM**—to maximize click-through and conversion rates[cite: 1, 2].

### 4. Market Basket Analysis (Products Sold Together)
- **Most Frequently Bundled Combinations:**
  1. **iPhone + Lightning Charging Cable** (1,005 transactions)[cite: 1, 2]
  2. **Google Phone + USB-C Charging Cable** (987 transactions)[cite: 1, 2]
  3. **iPhone + Wired Headphones** (447 transactions)[cite: 1, 2]
  4. **Google Phone + Wired Headphones** (414 transactions)[cite: 1, 2]
  5. **Vareebadd Phone + USB-C Charging Cable** (361 transactions)[cite: 1, 2]
- **Recommendation:** Implement automated checkout recommendation widgets and bundle promotions (e.g., *"Add a charging cable or headphones for 15% off"*) to increase Average Order Value (AOV)[cite: 2].

### 5. Product Volume vs. Price Elasticity
- **High-Volume Drivers:** Low-cost consumables and accessories (AAA/AA Batteries, USB-C & Lightning Cables) dominated overall unit order counts[cite: 1, 2].
- **Revenue Drivers:** Premium electronics (MacBook Pro, ThinkPad, high-end smartphones) have lower transaction volume but drive the majority of top-line revenue[cite: 1, 2].
- **Takeaway:** Accessory sales maintain steady transaction volume, while high-ticket items require focused retention and conversion strategies[cite: 1, 2].

---

## 🛠️ Data Pipeline & Workflow

1. **Ingestion & Merging:**
   - Consolidated 12 monthly CSV files from `./Sales_Data` into a single dataset (`all_data.csv`)[cite: 1, 2].
2. **Data Cleaning:**
   - Removed completely null records using `.dropna(how='all')`[cite: 1, 2].
   - Filtered out embedded repeating header rows (`Order Date != 'Or'`)[cite: 1, 2].
   - Cast numeric features (`Quantity Ordered` to integer, `Price Each` to float)[cite: 1, 2].
3. **Feature Engineering:**
   - Extracted `Month` and formatted `City (State)` to differentiate duplicate city names[cite: 1, 2].
   - Computed total order value: `Sales = Quantity Ordered * Price Each`[cite: 1, 2].
   - Derived `Hour` and `Minute` timestamps for time-of-day analytics[cite: 1, 2].
4. **Market Basket Analysis:**
   - Grouped multiple items ordered under the same `Order ID`[cite: 1, 2].
   - Utilized `itertools.combinations` and `collections.Counter` to identify co-purchased item pairs[cite: 1, 2].

---

## 📦 Requirements
- Python 3.7+[cite: 1, 2]
- `pandas`[cite: 1, 2]
- `matplotlib`[cite: 1, 2]

---

## 💻 Installation & Usage

```bash
# 1. Clone repository
git clone <repo-url>
cd <repo-folder>

# 2. Install dependencies
pip install pandas matplotlib

# 3. Launch notebook
jupyter notebook "Sales Analysis.ipynb"
