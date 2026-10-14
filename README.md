# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores 3,900 retail purchases to understand spending patterns, customer segments, product preferences, and subscription behavior. The workflow covers **Python (EDA & cleaning) → PostgreSQL (business queries) → Power BI (dashboard) → Report → Gamma PPT**.

---

## 📌 Overview

**Goal:** Turn raw transaction data into clear, actionable insights that can guide business decisions such as subscription growth, loyalty programs, discount policy, and targeted marketing.

**Key questions answered:**
- Which customer groups (gender, age) generate the most revenue?
- Do discounts and shipping types affect spending?
- Are subscribers more valuable than non-subscribers?
- Which products are top-rated, best-selling, or most discount-dependent?
- How are customers split into New, Returning, and Loyal segments?

---

## 📂 Dataset

| Item | Details |
|------|---------|
| Rows | 3,900 purchases |
| Columns | 18 |
| Missing data | 37 values in `Review Rating` |

**Feature groups**
- **Customer demographics:** Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method

> Dataset source: `<add link or name here>`

---

## 🧰 Tools & Technologies

| Purpose | Tool |
|---------|------|
| Data loading, EDA, cleaning | Python (`pandas`) |
| Database & SQL analysis | PostgreSQL (pgAdmin) |
| Dashboard | Power BI |
| Presentation | Gamma (PPT) |
| Reporting | Written project report (PDF) |

---

## 🔄 Project Steps

### 1. Data Loading & EDA (Python)
- Loaded the dataset with `pandas`
- Checked structure with `df.info()` and summary statistics with `df.describe()`

### 2. Data Cleaning & Feature Engineering
- **Missing values:** Filled missing `Review Rating` values using the **median rating of each product category**
- **Column names:** Standardized to `snake_case`
- **New features:** Created `age_group` (age binning) and `purchase_frequency_days`
- **Consistency check:** Found `discount_applied` and `promo_code_used` to be redundant, so dropped `promo_code_used`

### 3. SQL Analysis (PostgreSQL)
Loaded the cleaned DataFrame into PostgreSQL and answered 10 business questions:

1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average rating
4. Average spend: Standard vs. Express shipping
5. Subscribers vs. non-subscribers
6. Top 5 discount-dependent products
7. Customer segmentation (New / Returning / Loyal)
8. Top 3 products per category
9. Repeat buyers (>5 purchases) and subscription status
10. Revenue by age group

### 4. Dashboard (Power BI)
Built an interactive dashboard to present the findings visually (see below).

### 5. Report & Presentation
Documented the full process and insights in a report, and created a summary presentation using **Gamma**.

---

## 📊 Dashboard

**Customer Behavior Dashboard (Power BI)**

![Customer Behavior Dashboard](images/dashboard.png)

**KPIs:** 3.9K customers · $59.76 average purchase amount · 3.75 average review rating

**Visuals:** subscription split, revenue and sales by category, revenue and sales by age group

**Filters:** Subscription Status, Gender, Category, Shipping Type

---

## 📈 Results & Key Insights

- **Revenue by gender:** Male customers generated about **$157.9K** vs. **$75.2K** from female customers
- **Subscriptions:** Only **27%** of customers are subscribers, and subscribers spend about the same as non-subscribers (**$59.49 vs. $59.87** average)
- **Shipping:** Express shipping customers spend slightly more (**$60.48**) than Standard (**$58.46**)
- **Top-rated products:** Gloves (3.86), Sandals (3.84), Boots (3.82)
- **Most discount-dependent:** Hat (50.0%), Sneakers (49.7%), Coat (49.1%)
- **Customer segments:** 3,116 Loyal · 701 Returning · 83 New
- **Age groups:** Revenue is fairly even; Young Adults lead (**$62.1K**), followed by Middle-aged, Adult, and Senior
- **Top categories:** Clothing and Accessories drive the most revenue and sales

### 💡 Business Recommendations
- **Boost subscriptions** by promoting exclusive subscriber benefits
- **Launch loyalty programs** to reward repeat buyers
- **Review the discount policy** to balance sales boosts with margins
- **Improve product positioning** by highlighting top-rated and best-selling items
- **Target marketing** at high-revenue age groups and express-shipping users

---

## ▶️ How to Run

**1. Clone the repository**
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

**2. Install dependencies**
```bash
pip install pandas numpy sqlalchemy psycopg2-binary jupyter
```

**3. Run the Python notebook**
- Open the notebook in Jupyter and run all cells to load, clean, and explore the data
- Update the PostgreSQL connection details (host, port, database, user, password) in the notebook to load the cleaned data into your database

**4. Run the SQL queries**
- Open pgAdmin and run the queries in `sql/queries.sql` against the loaded table

**5. View the dashboard**
- Open `powerbi/Customer_Behavior_Dashboard.pbix` in Power BI Desktop

---

## 🗂️ Repository Structure

```
├── data/              # Raw and cleaned dataset
├── notebooks/         # Python EDA & cleaning notebook
├── sql/               # PostgreSQL queries
├── powerbi/           # Power BI dashboard (.pbix)
├── images/            # Dashboard screenshots
├── report/            # Project report (PDF)
├── presentation/      # Gamma presentation
└── README.md
```

---

## 👤 Author

**Vanka Nandini**
Data Analyst | MCA Graduate
📧 `<your-email>` · 🔗 `<LinkedIn URL>` · 💻 `<GitHub URL>`
