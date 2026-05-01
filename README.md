# Amazon Sales Data Analysis

A Python-based exploratory analysis of Amazon product listings, focused on how discounts, pricing, and ratings relate to each other across product categories.

---

## Objective

Understand whether discounts actually drive better customer ratings, and which categories and price segments perform best by review volume and satisfaction.

---

## Dataset

- **File:** `amazon_sales.csv`
- **Fields used:** `product_id`, `discounted_price`, `actual_price`, `discount_percentage`, `rating`, `rating_count`, `category`

---

## What This Notebook Does

### 1. Data Cleaning
- Removed duplicate products (deduplicated on `product_id`)
- Stripped currency symbols (₹) and commas from price columns
- Converted price, discount, rating, and rating count fields to numeric types
- Dropped rows with missing or non-numeric ratings and review counts

### 2. Feature Engineering
- **Savings:** Computed absolute savings per product (`actual_price - discounted_price`)
- **Price Segments:** Bucketed products into Budget (< ₹200), Mid (₹200–₹1000), and Premium (> ₹1000)
- **Weighted Rating:** Calculated rating weighted by review count for fairer category comparisons

### 3. Analysis Questions Answered
- Which 10 categories have the highest weighted ratings?
- Which 10 categories offer the highest average discounts?
- Does discounted price affect customer rating?
- Which products have the most reviews?
- Do heavily discounted categories also have high ratings?
- Does discount percentage correlate with review volume?
- How does average rating vary across price segments?

---

## Key Findings

- **Discounts don't improve satisfaction.** Correlation between discount percentage and rating is near zero — customers don't rate discounted products higher.
- **Discounts do drive volume.** Higher discount percentages correlate with more reviews, suggesting increased purchase activity.
- **Budget products rate slightly higher.** Products under ₹200 tend to have marginally better ratings, likely due to lower buyer expectations.

---

## Tools Used

| Tool | Purpose |
|---|---|
| `pandas` | Data cleaning, grouping, aggregation |
| `numpy` | Weighted calculations |
| `matplotlib` | Scatter plots and trend visualization |
| Jupyter Notebook | Analysis environment |

---

## Files

| File | Description |
|---|---|
| `Amazon_sales.ipynb` | Full analysis notebook |
| `amazon_sales.csv` | Raw dataset |

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/dsai04/Amazon_Sales.git
cd Amazon_Sales

# Install dependencies
pip install pandas numpy matplotlib jupyter

# Launch the notebook
jupyter notebook Amazon_sales.ipynb
```

> **Note:** The notebook originally uses a local file path (`C:/Users/Dhruv/...`). Update the `pd.read_csv()` path to point to `amazon_sales.csv` in the repo root before running.
