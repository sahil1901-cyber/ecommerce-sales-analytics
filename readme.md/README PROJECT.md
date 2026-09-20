# 🛒 Ecommerce Sales Analytics — Diagnostics & Business Insights

An end-to-end data analytics project on a simulated Indian ecommerce marketplace (Meesho / Myntra / Flipkart style) — covering data cleaning (Excel + Python), exploratory data analysis, and an interactive Power BI dashboard, with business recommendations tied to every insight.

---

## 📌 Problem Statement

Indian ecommerce marketplaces run on thin margins with heavy COD usage, high fashion-category return rates, and seasonal demand spikes. This project analyzes 100,000+ transactions to answer:

- Which categories, sellers, and cities drive the most revenue — and the most returns?
- How do COD vs Prepaid orders differ in return behavior?
- What impact do discounts and festive sales have on revenue and returns?
- How dependent is the business on repeat customers vs new acquisition?

---

## 🗂️ Dataset

- **Rows:** ~100,350 (including intentional duplicates)
- **Columns:** 13 — order details, customer, product, category, seller, city/tier, payment mode, quantity, price, discount %, return status
- **Time range:** Jan 2023 – Dec 2024
- **Note:** Dataset is synthetically generated to reflect realistic Indian marketplace patterns (COD-heavy tier-2/3 cities, fashion-driven returns, festive-season spikes) and intentionally includes real-world data issues — missing values, inconsistent labels, duplicates, and outliers — to demonstrate a full data-cleaning workflow.

---

## 🧹 1. Data Cleaning (Excel + Python)

- Initial pass in Excel — removed obvious duplicates, applied formatting/borders for readability
- Deeper cleaning done in Python (`notebooks/data_cleaning.ipynb`):

- Handled missing values in `seller_name`, `city`, `discount_percent`, `payment_mode`
- Standardized inconsistent `payment_mode` labels (`COD`, `cod`, `Cash on Delivery` → `COD`)
- Fixed inconsistent city name casing (`Mumbai`, `MUMBAI`, `mumbai` → `Mumbai`)
- Removed 350 duplicate order rows
- Corrected negative and extreme outlier price entries
- Saved cleaned output as `data/ecommerce_cleaned.csv`

---

## 📊 2. Exploratory Data Analysis (`notebooks/eda_analysis.ipynb`)

Key findings:

- **Category-wise revenue:** Women Ethnic Wear leads (~₹4.05 Cr), followed by Men's Fashion (~₹3.44 Cr). Kids Wear contributes the least (~₹0.52 Cr).
- **Seasonality:** October–November shows a sharp revenue spike each year (~₹1.7 Cr in 2023, ~₹1.9 Cr in 2024) driven by the festive/Diwali season — roughly 2–3x a normal month.
- **Payment mode & returns:** COD orders have a **16.8%** return rate vs **9.6%** for Prepaid — COD returns run ~75% higher.
- **City tier:** Average order value is nearly identical across Tier 1/2/3 (~₹1,925–₹1,940) — spending isn't concentrated in metros.
- **Discounting:** Return rate stays flat (~12.7–13.4%) up to 30% discount, then climbs to 17.7% beyond 40% discount — deep discounts appear to drive impulse buys that get returned.
- **Customer retention:** 96.4% of revenue comes from repeat customers, only 3.6% from new customers — a retention-heavy business model.

---

## 📈 3. Dashboard (`dashboard/Sales Dashboard 2023 & 24.pbix`)

Interactive Power BI dashboard featuring:
- 6 KPI cards — Total Revenue (₹193.33M), Total Orders (100K), Average Order Value (₹1.93K), Return Rate (14.20%), Total Sellers (417)
- Filled area chart — monthly revenue trend with festive-season spikes
- Category-wise revenue and return rate, split by year (2023 vs 2024)
- Donut charts — revenue by customer type (new vs repeat), revenue split by payment mode
- Pie chart — return rate by payment mode
- Slicers for Category, City Tier, and Payment Mode

📸 Screenshot available in `dashboard/dashboard_screenshots/`

---

## 💡 4. Business Recommendations

| Insight | Recommendation |
|---|---|
| COD return rate is 75% higher than Prepaid | Introduce confirmation calls or OTP verification for high-value COD orders to cut return-driven logistics costs |
| Revenue spikes 2–3x in Oct–Nov (festive season) | Plan inventory stocking and ad-spend 4–6 weeks ahead of the festive window |
| Discounts above 40% correlate with higher returns | Cap blanket discounting; use targeted coupons instead of flat deep discounts |
| 96.4% of revenue is repeat-customer driven | Retention is strong, but new-customer acquisition needs investment to avoid growth plateauing on the existing base |
| AOV is flat across city tiers | Marketing spend doesn't need to concentrate on metro cities — Tier 2/3 customers spend just as much per order |

---

## 🛠️ Tools Used

`Excel` · `Python (Pandas, NumPy, Matplotlib/Seaborn)` · `Power BI` · `Jupyter Notebook`

---

## 🚀 How to Run

```bash
git clone <your-repo-url>
cd ecommerce-sales-analytics
pip install pandas numpy matplotlib seaborn
jupyter notebook notebooks/data_cleaning.ipynb
```

Open `dashboard/Sales Dashboard 2023 & 24.pbix` in Power BI Desktop to explore the interactive dashboard.

---

## 📁 Repository Structure

```
ecommerce-sales-analytics/
├── data/
│   ├── ecommerce_sales_dataset.csv
│   └── ecommerce_cleaned.csv
├── notebooks/
│   ├── data_cleaning.ipynb
│   └── eda_analysis.ipynb
├── plots/
│   └── (EDA chart images)
├── dashboard/
│   ├── Sales Dashboard 2023 & 24.pbix
│   └── dashboard_screenshots/
├── README.md
```

---

## 👤 Author

*(Your name)* — Data Analyst
[LinkedIn](#) · [Portfolio](#)
