<div align="center">

# 💹 Financial Health Dashboard

### CodeAlpha Power BI Internship — Task 1

**Financial Analytics • Budgeting • Profitability • Forecasting • Decision Support**

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=000000)
![DAX](https://img.shields.io/badge/DAX-1F4E78?style=for-the-badge&logo=microsoft&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Financial Analytics](https://img.shields.io/badge/Financial%20Analytics-0E7490?style=for-the-badge)
![Forecasting](https://img.shields.io/badge/Forecasting-7C3AED?style=for-the-badge)

</div>

---

## 🎯 Project Overview

The **Financial Health Dashboard** is an interactive Power BI project created for the **CodeAlpha Power BI Internship — Task 1**.

The dashboard is designed to analyze the financial status of an SME by combining **income statement performance, balance sheet health, cash-flow movement, profitability analysis, budget comparison, and forecasting** into one decision-support solution.

The project helps answer questions such as:

- How much revenue and profit is the business generating?
- Are actual results meeting the budget?
- Which expense categories are driving costs?
- Is the business financially liquid?
- How are assets, liabilities, and equity positioned?
- What is the cash-flow position?
- What could future revenue look like?

---

# 📋 CodeAlpha Task Requirement

<p align="center">
  <img src="screenshots/task-requirement.png" alt="CodeAlpha Task 1 Financial Health Dashboard Requirement" width="950"/>
</p>

### Objective

Develop a dashboard analyzing an organization's financial status with real-time insights, particularly useful for SMEs.

### Key Requirements

- Visualize **Income Statements**
- Visualize **Balance Sheets**
- Visualize **Cash Flows**
- Analyze **profitability trends over time**
- Provide **forecasting for budgeting and financial planning**
- Deliver an **interactive Power BI report with actionable insights**

---

# 🧭 Dashboard Structure

The final report contains **three analytical pages**:

| Page | Purpose |
|---|---|
| 🟦 **Executive Overview** | Overall financial health and core KPIs |
| 🟩 **Income Statement Analysis** | Revenue, expenses, profitability and budget performance |
| 🟪 **Forecast & Planning** | Revenue forecast, variance analysis and financial planning |

---

# 🟦 Page 1 — Executive Overview

<p align="center">
  <img src="screenshots/overview.png" alt="Financial Health Dashboard Executive Overview" width="1100"/>
</p>

The **Executive Overview** acts as the financial command center of the report.

### 📌 Key KPIs

- Revenue
- Gross Profit
- Net Profit
- Net Profit Margin %
- Closing Assets
- Net Cash Flow

### 📊 Visuals

- Revenue vs Budget — Monthly
- Net Profit Margin Trend
- Profitability Trend — Monthly
- Cash Flow Summary
- Balance Sheet Summary
- Closing Assets
- Closing Liabilities
- Closing Equity
- Closing Current Ratio
- Closing Debt-to-Equity

### 🎛 Interactive Filters

- Year
- Quarter
- Month

This page gives management a quick snapshot of profitability, liquidity, leverage, and cash movement.

---

# 🟩 Page 2 — Income Statement Analysis

<p align="center">
  <img src="screenshots/income-statement.png" alt="Income Statement Analysis Dashboard" width="1100"/>
</p>

The **Income Statement Analysis** page provides deeper analysis of operating performance.

### 📌 Key KPIs

- Revenue
- Cost of Goods Sold (COGS)
- Gross Profit
- Operating Expenses
- Net Profit
- Net Profit Margin %

### 📊 Visuals

- Income Statement — Actual vs Budget
- Revenue vs Cost Trend
- Actual vs Budget — Revenue
- Actual vs Budget — Net Profit
- Operating Expense Breakdown
- Profitability Margin Trend

### 💡 Insights Enabled

This page helps identify:

- Whether revenue growth is strong enough to cover costs
- Which expense categories consume the most resources
- Where actual performance differs from budget
- Whether profitability is improving or weakening
- Which cost areas may require management attention

---

# 🟪 Page 3 — Forecast & Planning

<p align="center">
  <img src="screenshots/forecast-planning.png" alt="Forecast and Planning Dashboard" width="1100"/>
</p>

The **Forecast & Planning** page converts historical financial performance into forward-looking business information.

### 📌 Planning KPIs

- Actual Revenue
- Budget Revenue
- Revenue Variance %
- Profit Variance %

### 🔮 Forecasting & Planning Visuals

- Revenue Forecast — Next 6 Months
- Forecast Confidence Interval
- Actual Revenue vs Budget
- Actual vs Budget — Net Profit
- Budget variance monitoring

This page supports management in evaluating future performance and planning against expected financial targets.

---

# 📐 Important Financial Measures

| KPI / Measure | Purpose |
|---|---|
| **Revenue** | Total operating income |
| **COGS** | Direct cost of producing revenue |
| **Gross Profit** | Revenue minus COGS |
| **Gross Profit Margin %** | Gross Profit ÷ Revenue |
| **Operating Expenses** | Day-to-day operating costs |
| **Net Profit** | Profit after expenses and tax |
| **Net Profit Margin %** | Net Profit ÷ Revenue |
| **Closing Assets** | Latest available asset position |
| **Closing Liabilities** | Latest liability position |
| **Closing Equity** | Latest equity position |
| **Current Ratio** | Current Assets ÷ Current Liabilities |
| **Debt-to-Equity** | Liabilities ÷ Equity |
| **Net Cash Flow** | Net operating, investing and financing cash movement |
| **Revenue Variance %** | Actual Revenue vs Budget Revenue |
| **Profit Variance %** | Actual Profit vs Budget Profit |

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

### Revenue Variance %

```DAX
Revenue Variance % =
DIVIDE(
    [Revenue] - [Budget Revenue],
    [Budget Revenue],
    0
)
```

---

# 🗂️ Data Model

A dedicated Calendar table is connected to the financial fact table using a **one-to-many relationship**.

```text
┌─────────────────────┐
│      Calendar       │
│ Date / Month / Year │
│      Quarter        │
└──────────┬──────────┘
           │ 1
           │
           │ *
┌──────────▼──────────┐
│   Financial_Data    │
│ Income Statement    │
│ Balance Sheet       │
│ Cash Flow           │
│ Actual + Budget     │
└─────────────────────┘
```

The Calendar table supports:

- Year filtering
- Quarter filtering
- Month filtering
- Correct month sorting
- Month-over-Month calculations
- Year-over-Year calculations
- Forecasting

---

# 🔄 Project Workflow

```text
Financial Dataset
       ↓
Power Query Cleaning
       ↓
Data Type Validation
       ↓
Calendar Table
       ↓
Data Model Relationship
       ↓
DAX Measures
       ↓
Financial KPIs
       ↓
Actual vs Budget Analysis
       ↓
Profitability Analysis
       ↓
Balance Sheet & Cash Flow Analysis
       ↓
Revenue Forecasting
       ↓
Interactive Power BI Dashboard
```

---

# 🛠️ Tools & Technologies

| Technology | Usage |
|---|---|
| 🟨 **Microsoft Power BI Desktop** | Dashboard development |
| 🟦 **DAX** | Financial calculations and measures |
| 🟩 **Power Query** | Data cleaning and transformation |
| 📗 **Microsoft Excel** | Source dataset |
| 🐙 **GitHub** | Project documentation and portfolio hosting |

---

# 💼 Skills Demonstrated

![Data Cleaning](https://img.shields.io/badge/Data%20Cleaning-2563EB?style=flat-square)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-0F766E?style=flat-square)
![DAX](https://img.shields.io/badge/DAX-7C3AED?style=flat-square)
![KPI Design](https://img.shields.io/badge/KPI%20Design-E11D48?style=flat-square)
![Financial Ratios](https://img.shields.io/badge/Financial%20Ratios-0891B2?style=flat-square)
![Budget Analysis](https://img.shields.io/badge/Budget%20Analysis-F59E0B?style=flat-square)
![Forecasting](https://img.shields.io/badge/Forecasting-16A34A?style=flat-square)
![Dashboard Design](https://img.shields.io/badge/Dashboard%20Design-4338CA?style=flat-square)

---

# 💡 Business Value

The dashboard allows users to:

- Monitor revenue and profitability
- Compare actual results against budgets
- Detect cost pressure and overspending
- Identify major expense drivers
- Evaluate liquidity using the Current Ratio
- Evaluate leverage using Debt-to-Equity
- Monitor operating, investing and financing cash flows
- Track profitability trends over time
- Forecast future revenue
- Support budgeting and financial planning

---

# 📁 Repository Structure

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

# 🌟 Key Learning Outcomes

Through this project, I strengthened my practical understanding of:

- Financial analytics
- Power Query
- DAX calculations
- Data modeling
- KPI design
- Financial ratios
- Actual vs Budget analysis
- Profitability analysis
- Interactive report design
- Forecasting and financial planning
- Converting raw financial data into actionable insights

---

# 🏁 Project Status

<div align="center">

### ✅ CodeAlpha Power BI Internship
### ✅ Task 1 — Financial Health Dashboard
### ✅ Completed Successfully

**From financial data → to analysis → to insights → to better decisions.**

</div>

---

## ⚠️ Disclaimer

The dataset used in this project is **synthetic** and is intended only for educational, internship, and portfolio purposes. It does not represent the financial records of any real company.

---

<div align="center">

### ⭐ Thank you for exploring this project!

**Data becomes valuable when it supports better decisions.**

</div>
