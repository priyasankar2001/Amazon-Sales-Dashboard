# 🛒 Amazon Sales Intelligence Dashboard
### Excel-based Business Analytics Project

---

## 📌 Project Overview

Stepped into the role of a **Business Analyst** at a retail tech company to transform 
raw Amazon sales data into a dynamic Excel dashboard. Cleaned raw data, applied 
smart lookup formulas, built Pivot Tables, and designed KPI cards to support 
business decisions.

---

## 🎯 Business Problem

The sales department provided a raw dump of **100 sales transactions** across 
multiple regions, products, and customer profiles. Management needed a report to:
- Understand product and region performance
- Explore customer trends
- Measure fulfillment efficiency
- Identify cancellation patterns

---

## 🛠️ Tools & Techniques Used

| Tool/Technique | Purpose |
|---|---|
| Excel Pivot Tables | Sales summary by region and category |
| XLOOKUP | Cross-sheet customer and product matching |
| IF / IFERROR | Order status and delivery logic |
| Calculated Fields | Cancellation rate, Effective Sales |
| Slicers | Dynamic filtering by region and payment |
| Conditional Formatting | Highlight high/low performers |
| Pivot Charts | Visual representation of key metrics |

---

## 📊 Dataset Structure

**Main Tables:**
- **Orders** — 100 records with 20 columns
- **Customer Master** — 50 customers with city and state
- **Product Master** — 23 products with category and cost
- **Region Master** — Sales targets by region

**Key Columns in Orders Sheet:**
```
Order ID | Customer ID | Product ID | Region
Sale Price | Quantity | Total Amount | Payment Method
Delivery Status | Order Date | Delivery Date | Cancel Date
Delivery Time | Delivery Performance | Effective Sales
```

---

## 📋 Analysis Performed

### 1. Data Cleaning
- Standardized date formats across Order Date, Delivery Date, Cancel Date
- Removed blanks and extra spaces
- Standardized Region, Payment Method, and Delivery Status entries

### 2. Pivot Table Analysis
- **Total Sales by Region and Product Category**
- **Order Count by Delivery Status** (Delivered / Cancelled / In Transit)
- **Average Delivery Time by Region**
- **Cancellation Rate by Region**

### 3. XLOOKUP Implementation
```excel
=XLOOKUP(B2, Customer_Master!A:A, Customer_Master!B:B)
```
- Matched Customer ID → Customer Name from Customer Master sheet
- Matched Product ID → Product Category and Product Name

### 4. Calculated Columns
```excel
-- Delivery Performance
=IF(DeliveryDate-OrderDate<=2, "Fast", "Slow")

-- Order Status
=IF(CancelDate<>"", "Cancelled", "Delivered")

-- Effective Sales (Delivered orders only)
=IF(DeliveryStatus="Delivered", TotalAmount, 0)

-- Cancellation Rate
=CancelledOrders / TotalOrders
```

### 5. KPI Metrics Created
- 📦 **Total Revenue** — Sum of all effective sales
- ⚡ **% Fast Deliveries** — Orders delivered within 2 days
- 🏆 **Top Performing Regions** — By total sales amount
- 🛍️ **Highest Selling Product Category**

---

## 💡 Key Findings

| Metric | Finding |
|---|---|
| Top Product Category | Electronics (highest revenue) |
| Delivery Performance | Average delivery time ~4.2 days |
| Cancellation Analysis | Cancellation rates vary by region |
| Best Payment Method | Analyzed across all transaction types |

---

## 📁 Project Structure

```
Mini-Project-3/
│
├── Week 3 Dataset.xlsx       → Main Excel file with all analysis
│   ├── Orders                → Raw + cleaned transaction data  
│   ├── Customer Master       → Customer reference data
│   ├── Product Master        → Product reference data
│   ├── Region Master         → Regional sales targets
│   ├── Pivot Analysis Sheets → Multiple pivot table analyses
│   └── Dashboard             → Final KPI dashboard
│
├── MINI PROJECT - WEEK 03.docx  → Project requirements document
│
├── screenshots/
│   ├── dashboard_overview.png
│   ├── pivot_tables.png
│   └── kpi_cards.png
│
└── README.md
```

---

## 🔍 Business Recommendations

Based on the analysis:

1. **Delivery Improvement** — Regions with slow delivery performance 
   should review fulfillment partner efficiency
   
2. **Cancellation Reduction** — High cancellation regions need 
   targeted intervention to reduce revenue loss
   
3. **Product Focus** — Electronics drives maximum revenue; 
   inventory should be optimized for this category

4. **Payment Method Optimization** — Analysis of preferred payment 
   methods can help streamline checkout experience

---

## 🚀 Skills Demonstrated

- ✅ Data Cleaning and Preprocessing in Excel
- ✅ Advanced Excel Formulas (XLOOKUP, IF, IFERROR)
- ✅ Pivot Tables with Calculated Fields
- ✅ KPI Dashboard Design
- ✅ Business Intelligence and Reporting
- ✅ Data-driven Decision Making

---



