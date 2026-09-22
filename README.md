# Electronics-Retail-Sales-Analysis-Python-SQL-Power-Bi
# 📊 Electronics Retail Sales Analysis

**End-to-end data analysis project** identifying why an electronics e-commerce retailer loses ~33% of orders to cancellation, and evaluating whether its loyalty program and cross-sell strategy are actually driving revenue.

Data period: **September 2023 – September 2024** | 20K+ orders

---

## 🧩 Business Problem

> The company is losing an estimated **$21.38M a year to cancelled orders (33% cancellation rate)**, and does not know which payment methods, shipping types, or products are driving it. At the same time, it doesn't know whether its **loyalty program** is actually paying off, or whether **add-on/cross-sell products** are being fully leveraged as a revenue driver. This project analyzes 20K+ transactions to answer both questions and recommend where the business should act first.

This breaks into three sub-questions the dashboard answers:
1. **Where is revenue leaking?** (cancellations — by product, payment method, shipping type, month)
2. **Is the loyalty program working?** (spend, order frequency, cancellation, add-on uptake — members vs non-members)
3. **Is cross-sell being maximized?** (add-on attach rate, add-on revenue share, which add-on types perform)

---

## 🛠️ Tools & Workflow

```
[ Raw Data (Kaggle CSV) ] → [ Python / Pandas — Cleaning ] → [ SQL — Storage & Querying ] → [ Power BI — Visualization ]
                                                                        ↕
                                                              [ Excel — Cross-checking ]
```

- **Python (Pandas, Jupyter Notebook)** — data cleaning, type fixes, feature engineering
- **SQL** — structured storage and querying of the cleaned dataset
- **Power BI (DAX)** — 5-page interactive dashboard
- **Excel** — manual cross-validation of key aggregates

---

## 📁 Dataset

Raw source: Kaggle (electronics retail transactions).

**Columns after cleaning:**
`Customer ID, Age, Gender, Loyalty Member, Product Type, SKU, Rating, Order Status, Payment Method, Total Price, Unit Price, Quantity, Purchase Date, Shipping Type, Add-ons Purchased, Add-on Total, Sales Revenue, Order ID, Year, Day, Month, Age-Group`

**Cleaning steps performed:**
- Standardized column names and categorical text (Gender, Order Status, Payment Method, etc.)
- Converted Purchase Date to datetime; derived Year, Month, Day, Age-Group
- Handled blank `Add-ons Purchased` / `Add-on Total` (no add-on ≠ missing data)
- Removed duplicate records; validated `Total Price` against `Unit Price × Quantity`
- Engineered `Order ID`, `Sales Revenue`, and `Age-Group` bins for segmentation
- Cross-checked aggregate totals in Excel before loading into Power BI

---

## 📊 Dashboard Pages

| Page | Focus |
|---|---|
| **1. Overview** | Revenue, orders, AOV, rating, cancellation rate, monthly trend, top/bottom products |
| **2. Product** | Revenue & units by product/SKU, price vs rating, cancellation rate by SKU |
| **3. Customer** | Repeat customers, loyalty comparison, age/gender segmentation, top customers |
| **4. Order Cancellation** | Cancellation rate by payment method, shipping type, product, and month |
| **5. Cross-Sell** | Add-on revenue, attach rate, add-on type performance, loyalty comparison |

* my screenshots here — 

<img width="1061" height="596" alt="E Overview" src="https://github.com/user-attachments/assets/a2a1f3fc-534d-4edf-8566-3df6cf860d89" />

<img width="1066" height="597" alt="E Product" src="https://github.com/user-attachments/assets/5971b545-7a70-42d3-9fc2-0edd77708b0d" />

<img width="1062" height="597" alt="E Customer" src="https://github.com/user-attachments/assets/3c0a26e0-a3cf-4029-9a7f-20e423c13168" />

<img width="1062" height="592" alt="E Order Cancellation" src="https://github.com/user-attachments/assets/fc02a5dd-9e48-4fa2-a0ef-409cd86ab0a8" />

<img width="1062" height="597" alt="E Cross-Sell" src="https://github.com/user-attachments/assets/3de7aa9e-45c0-4661-a884-08ba8c3f6476" />

```

## 🔑 Key Insights

**Overview**
- Total Revenue **$43.47M** | Total Orders **20K** | AOV **$3.24K** | Avg Rating **3.09**
- Cancellation rate **33%**
- Smartphone leads on both units (22K) and revenue ($14.63M); Headphones is the weakest product on both counts
- Revenue is seasonal: September is the low point in both 2023 and 2024; January 2024 was the peak ($4.61M)

**Product**
- SKU1001 (Smartphone) is the standout value SKU — lowest price (~$21), highest rating (5.0)
- SKU1004 (Smartphone) is the weak spot — mid price (~$790), lowest rating (2.0), and the **highest cancellation rate (34%)**
- Revenue by product: Smartphone $14.6M → Smartwatch $9.6M → Laptop $8.5M → Tablet $7.9M → Headphones $2.8M

**Customer**
- Repeat customers are **45.31%** of the base but generate **53.59%** of revenue ($23.29M)
- **Non-loyalty members outperform loyalty members** on AOV ($2.2K vs $2.1K), orders per customer (1.48 vs 1.13), and total revenue ($34.18M vs lower)
- Cancellation rate is identical for both groups (33%) — the loyalty program shows no protective effect
- Customers aged 36–75 drive the most volume and revenue; 75+ is a minimal segment
- Gender split is close to even on both orders and revenue

**Order Cancellation**
- **33% cancellation rate → $21.38M in lost revenue**
- Credit Card has the highest cancellation rate (34%); Cash the lowest (31%)
- Express shipping cancels more than Standard shipping
- Cancellation rate is fairly flat (32–34%) across products and months — no single dominant driver, but Credit Card + Express stand out

**Cross-Sell**
- Add-on revenue is **$32.95M**, representing **75.81% of total revenue** and a **75.66% order attach rate**
- Accessory and Extended Warranty tie as the top-earning add-on types (~$3.7M each)
- Non-loyalty members spend more on add-ons than loyalty members — consistent with their higher overall spend


## 💡 Recommendations

| Problem | Evidence | Recommended Action |
|---|---|---|
| **Cancellations cost $21.38M/year** | 33% rate, worst with Credit Card (34%) & Express shipping | Audit the Credit Card checkout/fraud-hold flow and Express fulfillment process first — highest-leverage fix |
| **Loyalty program isn't delivering value** | Non-members beat members on AOV, order frequency, and add-on spend, with equal cancellation | Redesign the loyalty incentive structure, or reallocate its budget toward cross-sell promotion, which already drives ~76% of revenue |
| **SKU1004 underperforms** | Lowest rating (2.0) and highest cancellation (34%) of any SKU | Investigate product quality/listing accuracy and fulfillment for this SKU specifically |
| **Revenue dips every September** | Lowest-revenue month in both 2023 and 2024 | Plan a targeted promotion or inventory push ahead of September |

---


## 👤 Author

**SK Eyasin Ali**
B.Tech, Electronics & Communication Engineering — MAKAUT, 2026
[LinkedIn] · [GitHub]

---

## 🧰 Tools Used
`Python (Pandas)` · `Jupyter Notebook` · `SQL` · `Power BI (DAX)` · `Excel`
