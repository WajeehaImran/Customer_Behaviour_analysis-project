# 🛍️ Customer Shopping Behavior Analysis

> End-to-end data analysis project uncovering consumer spending patterns, customer segments, and purchase drivers — built with Python, PostgreSQL, Power BI, and Gamma.

---

## 📌 Overview

A leading retail company noticed shifts in purchasing patterns across demographics, product categories, and sales channels. This project analyzes **3,900 customer transactions** to answer the core business question:

> *"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"*

The analysis spans the full data workflow — from raw data cleaning to an interactive Power BI dashboard and an executive-ready Gamma presentation.

---

## 📁 Dataset

| Field        | Details                                          |
|--------------|--------------------------------------------------|
| **Rows**     | 3,900 transactions                               |
| **Columns**  | 18 features                                      |
| **Missing Data** | 37 null values in `Review Rating` column     |

**Feature Groups:**

| Group | Columns |
|-------|---------|
| Customer Demographics | Age, Gender, Location, Subscription Status |
| Purchase Details | Item Purchased, Category, Purchase Amount (USD), Season, Size, Color |
| Shopping Behavior | Discount Applied, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (Pandas) | EDA & Data Cleaning |
| SQL server | Structured querying & business analysis |
| Power BI | Interactive dashboard |
| Gamma | Presentation & report slides |
| Jupyter Notebook | Analysis documentation |

---

## 🔄 Project Steps

### Step 1 — Data Loading & Initial Exploration (Python)
- Imported dataset using `pandas`
- Used `df.info()` and `df.describe()` to inspect structure and summary statistics
- Identified 37 missing values in the `Review Rating` column

### Step 2 — Exploratory Data Analysis (EDA)
- Analyzed distributions, outliers, and correlations across all 18 features
- Visualized spending patterns by gender, age group, category, and season
- Explored discount usage and its relationship with purchase amounts

### Step 3 — Data Cleaning & Feature Engineering
- **Missing values:** Imputed `Review Rating` nulls using the **median rating per product category**
- **Column standardization:** Renamed all columns to `snake_case`
- **Feature engineering:**
  - Created `age_group` column by binning customer ages into Young Adult, Adult, Middle-aged, and Senior
  - Created `purchase_frequency_days` from purchase frequency data
- **Redundancy check:** Verified `discount_applied` and `promo_code_used` were redundant — dropped `promo_code_used`
- **Database integration:** Connected Python to PostgreSQL and loaded cleaned DataFrame for SQL analysis

### Step 4 — SQL Analysis (SQL server)
Ran 10 business queries to extract actionable insights:

| # | Query | Key Finding |
|---|-------|-------------|
| 1 | Revenue by Gender | Male: $157,890 — Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts yet spent above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| 4 | Shipping Type Comparison | Express avg: $60.48 — Standard avg: $58.46 |
| 5 | Subscribers vs. Non-Subscribers | Similar avg spend (~$59); subscribers = 1,053 vs 2,847 non-subscribers |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3,116 — Returning: 701 — New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | 2,518 repeat buyers are non-subscribers — conversion opportunity |
| 10 | Revenue by Age Group | Young Adult: $62,143 leads all segments |

### Step 5 — Power BI Dashboard
- Connected Power BI directly to PostgreSQL
- Built an interactive **Customer Behavior Dashboard** featuring:
  - KPI cards: 3.9K customers, $59.76 avg purchase, 3.75 avg review rating
  - Revenue and sales breakdown by category and age group
  - Subscription status donut chart (Yes: 27%, No: 73%)
  - Slicers for Subscription Status, Gender, Category, and Shipping Type

### Step 6 — Report & Presentation (Gamma)
- Compiled findings into a structured PDF report
- Built a stakeholder-ready presentation in **Gamma** with key insights, charts, and business recommendations

---

## 📊 Dashboard Preview

> **Customer Behavior Dashboard** — Power BI

| KPI | Value |
|-----|-------|
| Total Customers | 3,900 |
| Average Purchase Amount | $59.76 |
| Average Review Rating | 3.75 / 5 |
| Subscriber Rate | 27% |

Dashboard includes: Revenue by Category, Sales by Age Group, Subscription breakdown, and Category-level filters.

📎 [Add your Power BI link or screenshot here](./dashboard/dashboard_screenshot.png)

---

## 📈 Key Results & Business Recommendations

| Finding | Recommendation |
|---------|---------------|
| Only 27% of customers are subscribers despite similar avg spend | **Boost subscriptions** — promote exclusive subscriber benefits |
| 3,116 out of 3,900 customers are already in the Loyal segment | **Loyalty programs** — reward repeat buyers to retain them |
| Hat, Sneakers, and Coat have ~50% discount dependency | **Revisit discount policy** — avoid margin erosion on high-demand items |
| Young Adults generate the highest revenue ($62,143) | **Targeted marketing** — focus campaigns on 18–35 age group |
| Express shipping users spend slightly more ($60.48) | **Upsell shipping** — offer express as a premium add-on |
| Gloves, Sandals, and Boots are top-rated products | **Product positioning** — feature top-rated items in promotions |

---


## ▶️ How to Run

### Python — EDA & Cleaning
```bash
# 1. Clone the repository
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis

# 2. Install dependencies
pip install pandas matplotlib seaborn psycopg2 jupyter

# 3. Run the notebooks in order
jupyter notebook notebooks/01_load_and_eda.ipynb
jupyter notebook notebooks/02_data_cleaning.ipynb
```

### SQL server — SQL Queries
```sql
-- 1. Create a new database in SQL server (e.g., shopping_db)
-- 2. The Python cleaning notebook auto-loads cleaned_data into SQL server
-- 3. Then open and run:
--    sql/queries.sql
```

### Power BI — Dashboard
1. Open `dashboard/customer_behavior.pbix` in Power BI Desktop
2. Go to **Transform Data → Data Source Settings**
3. Update the PostgreSQL connection to your local server
4. Click **Refresh** — all visuals update automatically

---

## 👩‍💻 Author

**Wajeeha**  
Data Analyst | CS Student @ UET Lahore  


---

## 📄 License

This project is for educational and portfolio purposes.
