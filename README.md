# 🛒 BlinkIT Grocery Sales Analysis — Power BI Dashboard

> **An end-to-end Power BI analytics project** built on BlinkIT's grocery sales data — analysing $1.2M in total sales across 8,523 items, 10 outlets, 4 outlet types, and 3 location tiers to surface actionable business intelligence for retail strategy decisions.

---

## 📌 Project Overview

BlinkIT is India's last-minute grocery delivery app. This project transforms raw transactional grocery data into a fully interactive, single-page Power BI dashboard that answers the key business questions a retail operations manager or category analyst would ask every day:

- Which outlet type and tier drives the highest revenue?
- What item categories and fat-content preferences dominate sales?
- How does outlet establishment year correlate with sales performance?
- Which outlet size contributes the most to the bottom line?

The dashboard is designed for **executive-level readability** — all critical KPIs visible at a glance, with slicers for deep-dive filtering by outlet size, location tier, item type, and more.

---

## 📊 Dashboard Preview
<img width="1300" height="723" alt="Screenshot 2026-04-20 200459" src="https://github.com/user-attachments/assets/d9c3ec69-d3b6-48d2-b099-6d6e8af76df7" />


---

## 🔢 Key Metrics (Full Dataset — No Filters Applied)

| Metric | Value |
|---|---|
| Total Sales | **$1.20M** |
| Average Sales per Item | **$141** |
| Total Number of Items | **8,523** |
| Average Customer Rating | **4.0 / 5** |
| Total Unique Outlets | **10** |
| Outlet Establishment Range | **2011 — 2022** |

---

## 📁 Dataset Overview

**File:** `BlinkIT_Grocery_Data.xlsx`
**Rows:** 8,523 transactions
**Columns:** 12 fields

| Column | Description |
|---|---|
| `Item Fat Content` | Fat category of the item (Low Fat / Regular) |
| `Item Identifier` | Unique product code |
| `Item Type` | Product category (Fruits & Veg, Snack Foods, Dairy, etc.) |
| `Outlet Establishment Year` | Year the outlet was established (2011–2022) |
| `Outlet Identifier` | Unique outlet code |
| `Outlet Location Type` | City tier classification (Tier 1 / Tier 2 / Tier 3) |
| `Outlet Size` | Physical store size (Small / Medium / High) |
| `Outlet Type` | Store format (Supermarket Type1/2/3, Grocery Store) |
| `Item Visibility` | Shelf visibility score of the item |
| `Item Weight` | Weight of the item in kg |
| `Sales` | Total sales value in USD |
| `Rating` | Average customer rating |

> **Data Quality Note:** The `Item Fat Content` column contained 5 inconsistent labels (`Low Fat`, `LF`, `low fat`, `Regular`, `reg`). These were standardised to two clean categories — **Low Fat** and **Regular** — during the data preparation phase before building the dashboard.

---

## 📈 Key Business Insights

### 1. Sales by Outlet Type
| Outlet Type | Total Sales | Item Count |
|---|---|---|
| Supermarket Type1 | $787,550 | 5,577 |
| Grocery Store | $151,939 | 1,083 |
| Supermarket Type2 | $131,478 | 928 |
| Supermarket Type3 | $130,715 | 935 |

> **Insight:** Supermarket Type1 dominates with **65.6% of total sales** despite having only 4 outlet types. Grocery Stores contribute $151K but with the fewest items per outlet — suggesting higher per-category concentration.

---

### 2. Sales by Location Tier
| Location Tier | Total Sales |
|---|---|
| Tier 3 | $472,133 |
| Tier 2 | $393,151 |
| Tier 1 | $336,398 |

> **Insight:** Tier 3 cities outperform Tier 1 cities by **40.3%** in total sales — counter-intuitive but typical of India's grocery delivery landscape where metro saturation pushes demand to smaller cities.

---

### 3. Sales by Outlet Size
| Outlet Size | Total Sales |
|---|---|
| Medium | $507,896 |
| Small | $444,794 |
| High | $248,992 |

> **Insight:** Medium-sized outlets generate the highest revenue, outperforming large (High) outlets. This suggests optimal store size for inventory turnover is mid-range, not maximum.

---

### 4. Top 5 Item Categories by Sales
| Item Type | Total Sales |
|---|---|
| Fruits and Vegetables | $178,124 |
| Snack Foods | $175,434 |
| Household | $135,977 |
| Frozen Foods | $118,559 |
| Dairy | $101,276 |

> **Insight:** Fruits & Vegetables and Snack Foods are neck-and-neck at the top — together accounting for **29.5% of total sales**. These two categories should be prioritised for inventory and promotional campaigns.

---

### 5. Fat Content Distribution
| Fat Content | Total Sales |
|---|---|
| Low Fat (all variants) | ~$776,320 |
| Regular (all variants) | ~$425,362 |

> **Insight:** Low Fat products account for **64.6% of sales** — a clear consumer health preference trend that should inform BlinkIT's sourcing and listing strategy.

---

### 6. Outlet Establishment Trend
Outlets established in **2018** generated peak sales of **$204.5K**, while the oldest outlets (2010–2011) show lower figures due to smaller initial inventory ranges. The trend shows consistent mid-range performance after 2015.

---

## 🛠 Tools & Technologies Used

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard design, data modelling, visualisation |
| **DAX (Data Analysis Expressions)** | KPI measures — Total Sales, Avg Sales, Item Count, Avg Rating |
| **Power Query (M Language)** | Data cleaning — standardising fat content labels, handling nulls |
| **Microsoft Excel (.xlsx)** | Source data format |
| **GitHub** | Project version control and portfolio hosting |

---

## 📐 DAX Measures Used

```dax
Total Sales = SUM(BlinkIT_Grocery_Data[Sales])

Average Sales = AVERAGE(BlinkIT_Grocery_Data[Sales])

Number of Items = COUNTROWS(BlinkIT_Grocery_Data)

Average Rating = AVERAGE(BlinkIT_Grocery_Data[Rating])
```

---

## 🎛 Dashboard Features

- **4 Interactive Slicers** — Filter by Outlet Size, Outlet Location Type, Item Type, and Outlet Type
- **Clear All Slicers Button** — Instant reset to full dataset view
- **4 KPI Cards** — Total Sales, Average Sales, Number of Items, Average Rating
- **Fat Content Donut Chart** — Low Fat vs Regular split with $ values
- **Fat by Outlet Stacked Bar** — Fat content breakdown across Tier 1, 2, and 3
- **Item Type Horizontal Bar** — Top 12 categories ranked by sales
- **Outlet Establishment Area Chart** — Historical sales trend from 2010–2022
- **Outlet Size Pie Chart** — Revenue share by store size
- **Outlet Location Bar Chart** — Tier-wise revenue comparison
- **Outlet Type Bar Chart** — Store format performance with item count overlay

---

## 🗂 Repository Structure

```
blinkit-grocery-sales-powerbi/
│
├── 📄 README.md                        ← You are here
├── 📊 BlinkIT_Grocery_Sales.pbix       ← Power BI dashboard file
├── 📁 data/
│   └── 📄 BlinkIT_Grocery_Data.xlsx   ← Raw source data (8,523 rows)
└── 📁 assets/
    └── 🖼 dashboard_screenshot.png     ← Dashboard preview image
```

---

## 🚀 How to Run This Project

```bash
# Step 1 — Clone this repository
git clone https://github.com/bisht5431-source/blinkit-grocery-sales-powerbi.git

# Step 2 — Open Power BI Desktop
# (Download free from https://powerbi.microsoft.com/desktop)

# Step 3 — Open the .pbix file
# File → Open → BlinkIT_Grocery_Sales.pbix

# Step 4 — Explore the dashboard
# Use the slicers on the left panel to filter and explore
```

---

## 💡 What I Learned From This Project

- How to **clean inconsistent categorical data** (5 fat content labels → 2 clean categories) using Power Query
- How to write **DAX measures** for KPI cards that respond dynamically to slicer selections
- How to design a **single-page dashboard** that communicates all key insights without overwhelming the viewer
- How **outlet size and location tier** interact with revenue in non-obvious ways (Tier 3 > Tier 1, Medium > High)
- How to use **donut, bar, area, and pie charts** together without creating visual clutter
- How to implement a **"Clear All Slicers" button** using Power BI bookmarks for better UX

---

## 📬 Connect With Me

| Platform | Link |
|---|---|
| LinkedIn | [linkedin.com/in/dataanalyst-manish](https://www.linkedin.com/in/dataanalyst-manish) |
| GitHub | [github.com/bisht5431-source](https://github.com/bisht5431-source) |
| Email | alphainsights123@gmail.com |


---

*Built as part of my Data Analyst portfolio | Manish Bisht*
