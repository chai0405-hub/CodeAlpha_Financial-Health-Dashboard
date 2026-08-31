<div align="center">

# 💹 Financial Health Dashboard

### CodeAlpha Power BI Internship — Task 1

**Interactive Financial Analytics • Budgeting • Profitability • Forecasting**

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=000000)
![DAX](https://img.shields.io/badge/DAX-1F4E78?style=for-the-badge&logo=microsoft&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Financial Analytics](https://img.shields.io/badge/Financial%20Analytics-0E7490?style=for-the-badge)
![Forecasting](https://img.shields.io/badge/Forecasting-7C3AED?style=for-the-badge)

</div>

---

## 🎯 Project Mission

The **Financial Health Dashboard** is an interactive Power BI solution designed to transform raw financial records into meaningful business insights for an SME.

The dashboard brings together:

- 💰 **Income Statement Analysis**
- 🏦 **Balance Sheet Monitoring**
- 💵 **Cash Flow Analysis**
- 📈 **Profitability Trends**
- 🎯 **Actual vs Budget Performance**
- 🔮 **Revenue Forecasting**
- 📊 **Interactive Financial KPIs**

> **Goal:** Help decision-makers understand what happened, why it happened, and what may happen next.

---

## 📋 CodeAlpha Task Requirement

<p align="center">
  <img src="screenshots/task-requirement.png" alt="CodeAlpha Task 1 Requirement" width="900"/>
</p>

### Required Deliverable

> An interactive Power BI report with dynamic visualizations and actionable financial insights.

---

# 🧭 Dashboard Architecture

The final solution contains **3 purpose-built analytical pages**:

<div align="center">

| Page | Focus |
|---|---|
| 🟦 **Executive Overview** | Overall financial health |
| 🟩 **Income Statement Analysis** | Revenue, cost, profit & budget performance |
| 🟪 **Forecast & Planning** | Future outlook, variance & planning |

</div>

---

# 🟦 1. Executive Overview

<p align="center">
  <img src="screenshots/overview.png" alt="Executive Overview Dashboard" width="1000"/>
</p>

The Executive Overview acts as the **financial command center**.

### 🔹 Core KPIs

| KPI | Business Meaning |
|---|---|
| 💰 Revenue | Total operating income |
| 📈 Gross Profit | Revenue after direct costs |
| 💵 Net Profit | Final profitability |
| 📊 Net Profit Margin % | Profitability efficiency |
| 🏦 Closing Assets | Latest asset position |
| 💳 Net Cash Flow | Net movement of cash |

### 🔹 Visual Analysis

- Revenue vs Budget — Monthly
- Net Profit Margin Trend
- Profitability Trend
- Cash Flow Summary
- Balance Sheet Summary
- Current Ratio
- Debt-to-Equity Ratio
- Interactive Year / Quarter / Month filters

---

# 🟩 2. Income Statement Analysis

<p align="center">
  <img src="screenshots/income-statement.png" alt="Income Statement Analysis Dashboard" width="1000"/>
</p>

This page dives deeper into **operating performance and profitability**.

### 🔹 KPIs

- Revenue
- Cost of Goods Sold (COGS)
- Gross Profit
- Operating Expenses
- Net Profit
- Net Profit Margin %

### 🔹 Analytical Visuals

- **Income Statement — Actual vs Budget**
- **Revenue vs Cost Trend**
- **Actual vs Budget — Revenue**
- **Actual vs Budget — Net Profit**
- **Operating Expense Breakdown**
- **Profitability Margin Trend**

### 💡 Business Value

This page helps identify:

- Which costs are increasing
- Whether revenue is covering operating expenses
- Where actual results deviate from budget
- Which expense categories require management attention
- Whether profitability is improving or weakening

---

# 🟪 3. Forecast & Planning

<p align="center">
  <img src="screenshots/forecast-planning.png" alt="Forecast and Planning Dashboard" width="1000"/>
</p>

The final page turns historical data into a **forward-looking financial planning tool**.

### 🔹 Planning KPIs

- Actual Revenue
- Budget Revenue
- Revenue Variance %
- Profit Variance %

### 🔹 Forecasting Features

- 🔮 **Revenue Forecast — Next 6 Months**
- 📉 Forecast confidence interval
- 🎯 Actual Revenue vs Budget
- 💹 Actual vs Budget — Net Profit
- 📊 Budget variance monitoring

> This page supports management in evaluating whether future financial targets appear achievable.

---

# 📐 Key Financial Measures

| Measure | Formula / Interpretation |
|---|---|
| **Gross Profit** | Revenue − COGS |
| **Net Profit** | Gross Profit − Operating Expenses − Other Expense − Tax |
| **Gross Profit Margin %** | Gross Profit ÷ Revenue |
| **Net Profit Margin %** | Net Profit ÷ Revenue |
| **Current Ratio** | Current Assets ÷ Current Liabilities |
| **Debt-to-Equity** | Total Liabilities ÷ Total Equity |
| **Revenue Variance %** | (Actual Revenue − Budget Revenue) ÷ Budget Revenue |

---

# 🧮 Selected DAX Measures

### Revenue

```DAX
Revenue =
CALCULATE(
    [Total Actual],
    Financial_Data[Statement] = "Income Statement",
    Financial_Data[Category] = "Revenue"
)
```

### Gross Profit

```DAX
Gross Profit =
[Revenue] - [COGS]
```

### Net Profit

```DAX
Net Profit =
[Gross Profit]
- [Operating Expenses]
- [Other Expense]
- [Tax Expense]
```

### Net Profit Margin %

```DAX
Net Profit Margin % =
DIVIDE(
    [Net Profit],
    [Revenue],
    0
)
```

### Closing Current Ratio

```DAX
Closing Current Ratio =
DIVIDE(
    [Closing Current Assets],
    [Closing Current Liabilities],
    0
)
```

### Closing Debt to Equity

```DAX
Closing Debt to Equity =
DIVIDE(
    [Closing Liabilities],
    [Closing Equity],
    0
)
```

---

# 🗂️ Data Model

```text
┌─────────────────┐
│    Calendar     │
│  Date / Month   │
│ Quarter / Year  │
└────────┬────────┘
         │ 1
         │
         │ *
┌────────▼────────────┐
│   Financial_Data    │
│ Income Statement    │
│ Balance Sheet       │
│ Cash Flow           │
│ Actual + Budget     │
└─────────────────────┘
```

The dedicated **Calendar table** supports:

- Month sorting
- Year filtering
- Quarter filtering
- Month-over-Month analysis
- Year-over-Year analysis
- Forecasting

---

# 🧹 Project Workflow

```text
Raw Financial Dataset
        ↓
Power Query Cleaning
        ↓
Data Type Validation
        ↓
Calendar Table Creation
        ↓
Data Model Relationship
        ↓
DAX Financial Measures
        ↓
KPI Development
        ↓
Actual vs Budget Analysis
        ↓
Profitability Analysis
        ↓
Balance Sheet & Cash Flow
        ↓
Revenue Forecasting
        ↓
Interactive Power BI Dashboard
```

---

# 🛠️ Tools & Technologies

<div align="center">

| Technology | Purpose |
|---|---|
| 🟨 **Microsoft Power BI Desktop** | Dashboard development |
| 🟦 **DAX** | Financial calculations & KPIs |
| 🟩 **Power Query** | Data cleaning & transformation |
| 📗 **Microsoft Excel** | Source financial dataset |
| 🐙 **GitHub** | Documentation & portfolio hosting |

</div>

---

# 💼 Skills Demonstrated

![Data Cleaning](https://img.shields.io/badge/Data%20Cleaning-2563EB?style=flat-square)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-0F766E?style=flat-square)
![DAX](https://img.shields.io/badge/DAX-7C3AED?style=flat-square)
![KPI Design](https://img.shields.io/badge/KPI%20Design-E11D48?style=flat-square)
![Budget Analysis](https://img.shields.io/badge/Budget%20Analysis-F59E0B?style=flat-square)
![Financial Ratios](https://img.shields.io/badge/Financial%20Ratios-0891B2?style=flat-square)
![Forecasting](https://img.shields.io/badge/Forecasting-16A34A?style=flat-square)
![Dashboard Design](https://img.shields.io/badge/Dashboard%20Design-4338CA?style=flat-square)

---

# 💡 Business Insights Enabled

The dashboard helps decision-makers:

- 📈 Monitor revenue and profitability
- 🎯 Compare actual performance against budget
- 💸 Detect overspending and cost pressure
- 🧾 Identify major operating-expense drivers
- 💧 Evaluate liquidity using the Current Ratio
- ⚖️ Monitor leverage using Debt-to-Equity
- 💵 Understand operating, investing and financing cash flows
- 🔮 Estimate future revenue
- 📊 Support budgeting and financial planning

---

# 📁 Suggested Repository Structure

```text
Financial-Health-Dashboard/
│
├── CodeAlpha_Task1_Financial_Health_Dashboard.pbix
├── Financial_Health_Dataset.xlsx
├── README.md
│
└── screenshots/
    ├── task-requirement.png
    ├── overview.png
    ├── income-statement.png
    └── forecast-planning.png
```

---

# 🌟 What I Learned

This project strengthened my practical understanding of:

- Financial statement analysis
- DAX measure creation
- Filter context
- Financial ratio calculations
- Budget variance analysis
- Power BI forecasting
- Interactive dashboard design
- Converting raw financial data into actionable business insights

---

# 🏁 Final Result

<div align="center">

### ✅ CodeAlpha Power BI Internship  
### ✅ Task 1 — Financial Health Dashboard  
### ✅ Completed Successfully

**From raw financial data → to insights → to better decisions.**

</div>

---

## ⚠️ Disclaimer

The financial dataset used in this project is **synthetic** and was created solely for educational, internship, and portfolio purposes. It does not represent the financial records of any real organization.

---

<div align="center">

### ⭐ If you find this project useful, consider starring the repository!

**Data becomes powerful when it supports better decisions.**

</div>
