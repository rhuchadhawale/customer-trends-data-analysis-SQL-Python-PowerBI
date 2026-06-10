# 🛍️ Customer Shopping Behavior Analysis

## 📌 Project Overview
An end-to-end data analytics project analyzing **3,900 customer transactions** across multiple product categories to uncover spending patterns, customer segments, product preferences, and subscription behavior — enabling data-driven business decisions.

---

## 🛠️ Tools & Technologies
| Tool | Purpose |
|------|---------|
| Python (Pandas, Matplotlib, Seaborn) | Data cleaning, EDA, feature engineering |
| PostgreSQL | Structured business queries and SQL analysis |
| Power BI | Interactive dashboard and KPI visualization |
| Excel | Initial data exploration |

---

## 📂 Dataset Summary
- **Rows:** 3,900 transactions
- **Columns:** 18 features
- **Key Features:**
  - Customer demographics: Age, Gender, Location, Subscription Status
  - Purchase details: Item, Category, Amount (USD), Season, Size, Color
  - Behavior metrics: Discount Applied, Previous Purchases, Frequency, Review Rating, Shipping Type
- **Missing Data:** 37 null values in Review Rating — imputed using median per product category

---

## 🔄 Project Workflow

### 1️⃣ Data Cleaning & Preprocessing (Python)
- Loaded dataset using **Pandas** and explored structure with `df.info()` and `df.describe()`
- Handled 37 missing Review Rating values using **category-wise median imputation**
- Renamed columns to **snake_case** for consistency
- **Feature Engineering:**
  - Created `age_group` column by binning customer ages into Young Adult, Adult, Middle-aged, Senior
  - Created `purchase_frequency_days` from purchase history
- Dropped redundant `promo_code_used` column after verifying overlap with `discount_applied`
- Connected Python script to **PostgreSQL** and loaded cleaned data for SQL analysis

### 2️⃣ SQL Analysis (PostgreSQL) — 10 Business Questions Answered
| # | Analysis | Key Finding |
|---|----------|-------------|
| 1 | Revenue by Gender | Male customers generated $157,890 vs Female $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts yet spent above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| 4 | Shipping Type Comparison | Express ($60.48) vs Standard ($58.46) avg spend |
| 5 | Subscribers vs Non-Subscribers | Similar avg spend (~$59) but 73% are non-subscribers |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3116 \| Returning: 701 \| New: 83 |
| 8 | Top 3 Products per Category | Used RANK() window function for category-wise ranking |
| 9 | Repeat Buyers & Subscriptions | 2,518 repeat buyers are non-subscribers — conversion opportunity |
| 10 | Revenue by Age Group | Young Adults lead at $62,143 total revenue |

### 3️⃣ Power BI Dashboard
Built an **interactive Customer Behavior Dashboard** featuring:
- KPI cards: Total Customers (3.9K), Avg Purchase Amount ($59.76), Avg Review Rating (3.75)
- Revenue & Sales by Category (Clothing leads)
- Revenue & Sales by Age Group
- Subscription Status donut chart (Yes 27% vs No 73%)
- Slicers for: Subscription Status, Gender, Category, Shipping Type

---

## 💡 Key Business Insights
1. **73% of customers are non-subscribers** — major opportunity to grow subscription revenue through targeted campaigns
2. **Young Adults (18–35) are the highest revenue segment** — prioritize marketing spend here
3. **839 high-value customers used discounts** yet still spent above average — discounts are not hurting premium buyers
4. **Hats, Sneakers, and Coats are discount-dependent** — review discount strategy for these products to protect margins
5. **2,518 repeat buyers have not subscribed** — loyalty program nudge could convert them

---

## 📊 Business Recommendations
- **Boost Subscriptions:** Offer exclusive early access or discounts to convert the 73% non-subscriber base
- **Loyalty Program:** Reward repeat buyers to push them into the Loyal segment
- **Review Discount Policy:** Balance sales boost with margin protection — especially for Hat, Sneakers, Coat
- **Targeted Marketing:** Focus campaigns on Young Adults and Express-shipping users — highest spend segments
- **Product Positioning:** Highlight top-rated products (Gloves, Sandals, Boots) in promotional campaigns

---

## 📁 Project Structure
```
customer-shopping-behavior-analysis/
│
├── data/
│   └── shopping_behavior.csv
│
├── python/
│   └── eda_cleaning.ipynb
│
├── sql/
│   └── business_queries.sql
│
├── powerbi/
│   └── customer_behavior_dashboard.pbix
│
└── README.md
```

---

## 🚀 How to Run
1. Clone this repository
2. Run `eda_cleaning.ipynb` in Jupyter Notebook for data cleaning steps
3. Load cleaned data into PostgreSQL and run `business_queries.sql`
4. Open `customer_behavior_dashboard.pbix` in Power BI Desktop

---

## 👩‍💻 Author
**Rhucha Dhawale**
Data Analyst | SQL • Python • Power BI
[LinkedIn](https://linkedin.com/in/rhucha-dhawale-157163284) | [GitHub](https://github.com/rhuchadhawale)
