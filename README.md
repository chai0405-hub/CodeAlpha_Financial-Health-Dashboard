# Financial Health Dashboard — Power BI

> **CodeAlpha Power BI Internship | Task 1**  
> Turning financial statements into an interactive decision-support dashboard for SMEs.

---

## Project Overview

The **Financial Health Dashboard** is an interactive Power BI solution designed to help a small or medium-sized enterprise understand its financial position at a glance.

Instead of reviewing separate spreadsheets for revenue, expenses, balance sheet items, cash flows, and budgets, this project brings them together into one analytical experience.

The dashboard answers practical business questions such as:

- Is the company profitable?
- Is revenue growing faster than expenses?
- Are actual results meeting the budget?
- How strong is the company's liquidity position?
- What is driving operating expenses?
- How much cash is generated from operating activities?
- What could revenue look like over the next six months?

---

## CodeAlpha Task Objective

**Task 1: Financial Health Dashboard**

The objective was to develop a Power BI dashboard that:

- Visualizes **Income Statements**
- Visualizes **Balance Sheets**
- Visualizes **Cash Flows**
- Analyzes **profitability trends over time**
- Supports **budgeting and financial planning**
- Provides **forecasting**
- Delivers dynamic visualizations and actionable insights

---

# Dashboard Architecture

The final report is organized into **three analytical pages**.

## 1. Executive Overview

The Overview page acts as the financial command center.

### Key KPIs

- Revenue
- Gross Profit
- Net Profit
- Net Profit Margin %
- Closing Assets
- Net Cash Flow

### Visual Analysis

- Revenue vs Budget — Monthly
- Net Profit Margin Trend
- Profitability Trend
- Cash Flow Summary
- Balance Sheet Summary
- Current Ratio
- Debt-to-Equity Ratio

### Interactive Filters

- Year
- Quarter
- Month

This page helps management understand the organization's overall financial health within seconds.

---

## 2. Income Statement Analysis

This page provides a deeper look at operating performance.

### KPIs

- Revenue
- Cost of Goods Sold (COGS)
- Gross Profit
- Operating Expenses
- Net Profit
- Net Profit Margin %

### Visuals

- Income Statement — Actual vs Budget
- Revenue vs Cost Trend
- Actual vs Budget — Revenue
- Actual vs Budget — Net Profit
- Operating Expense Breakdown
- Profitability Margin Trend

The purpose of this page is to identify where revenue is being generated, where money is being spent, and how those movements affect profitability.

---

## 3. Forecast & Planning

The final page focuses on forward-looking financial analysis.

### Planning KPIs

- Actual Revenue
- Budget Revenue
- Revenue Variance %
- Profit Variance %

### Forecasting & Budgeting Visuals

- Revenue Forecast — Next 6 Months
- Actual Revenue vs Budget
- Actual vs Budget — Net Profit
- Forecast confidence interval

This page converts historical financial performance into a planning tool for future decision-making.

---

# Key Financial Metrics Used

| Metric | Purpose |
|---|---|
| Revenue | Measures total operating income |
| COGS | Measures direct cost of generating revenue |
| Gross Profit | Revenue minus COGS |
| Gross Profit Margin % | Measures core business profitability |
| Operating Expenses | Tracks day-to-day operating costs |
| Net Profit | Final profit after expenses and tax |
| Net Profit Margin % | Measures profit retained from revenue |
| Closing Assets | Latest available asset position |
| Closing Liabilities | Latest liability position |
| Closing Equity | Latest equity position |
| Current Ratio | Evaluates short-term liquidity |
| Debt-to-Equity | Evaluates financial leverage |
| Net Cash Flow | Measures overall cash movement |
| Revenue Variance % | Compares actual revenue against budget |
| Profit Variance % | Compares actual profit against budget |

---

# Selected DAX Measures

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

### Current Ratio

```DAX
Closing Current Ratio =
DIVIDE(
    [Closing Current Assets],
    [Closing Current Liabilities],
    0
)
```

### Debt-to-Equity

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

# Data Model

A dedicated Calendar table is connected to the financial fact table using a **one-to-many relationship**.

```text
Calendar
   1
   |
   |
   *
Financial_Data
```

The Calendar table supports:

- Year filtering
- Quarter filtering
- Month filtering
- Month sorting
- Month-over-Month analysis
- Year-over-Year analysis
- Forecasting

---

# Dataset

The project uses a **synthetic SME financial dataset** created specifically for analytics practice.

### Coverage

- Historical period: **January 2024 onward**
- Actual financial data
- Budget financial data
- Income Statement records
- Balance Sheet snapshots
- Cash Flow records
- Monthly reporting structure

> The dataset is fictional and is intended only for educational, internship, and portfolio purposes.

---

# Power BI Features Demonstrated

This project demonstrates practical use of:

- Power Query
- Data Cleaning
- Data Transformation
- Data Modeling
- DAX Measures
- Filter Context
- Time Intelligence
- KPI Design
- Slicers
- Matrix Visuals
- Line Charts
- Clustered Column Charts
- Bar Charts
- Financial Ratios
- Budget Variance Analysis
- Revenue Forecasting
- Confidence Intervals
- Interactive Dashboard Design

---

# Project Workflow

```text
Raw Financial Data
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
Cash Flow & Balance Sheet Analysis
        ↓
Revenue Forecasting
        ↓
Interactive Power BI Dashboard
```

---

# Business Insights Enabled

The dashboard allows decision-makers to:

- Monitor revenue and profit performance
- Compare actual results with financial targets
- Detect cost pressure and overspending
- Identify major operating-expense drivers
- Evaluate liquidity through the Current Ratio
- Monitor financial leverage through Debt-to-Equity
- Understand operating, investing, and financing cash flows
- Track profitability trends over time
- Estimate future revenue using forecasting
- Support budgeting and financial planning

---

# Dashboard Screenshots

Create a `screenshots` folder in this repository and add your dashboard images using the following names:

```text
screenshots/
├── overview.png
├── income-statement.png
└── forecast-planning.png
```

Then use:

```md
![Executive Overview](screenshots/overview.png)
![Income Statement Analysis](screenshots/income-statement.png)
![Forecast & Planning](screenshots/forecast-planning.png)
```

---

# Repository Structure

```text
Financial-Health-Dashboard/
│
├── CodeAlpha_Task1_Financial_Health_Dashboard.pbix
├── Financial_Health_Dataset.xlsx
├── README.md
│
└── screenshots/
    ├── overview.png
    ├── income-statement.png
    └── forecast-planning.png
```

---

# Tools & Technologies

| Tool | Usage |
|---|---|
| Microsoft Power BI Desktop | Dashboard development |
| Power Query | Data cleaning and transformation |
| DAX | Financial calculations and KPIs |
| Microsoft Excel | Source dataset |
| GitHub | Project documentation and portfolio hosting |

---

# Skills Strengthened

Building this project strengthened my understanding of:

- Financial analytics
- Business intelligence
- KPI selection
- DAX calculations
- Data modeling
- Budget variance analysis
- Financial statement interpretation
- Dashboard storytelling
- Forecasting
- Turning raw data into actionable insights

---

# Why This Project Matters

A good dashboard should do more than display numbers.

It should help someone decide:

> **What happened?**  
> **Why did it happen?**  
> **Is the business financially healthy?**  
> **What should we watch next?**

That is the goal of this Financial Health Dashboard.

---

## Internship

**CodeAlpha Power BI Internship**  
**Task 1 — Financial Health Dashboard**

---

## Disclaimer

This project was created for educational and internship portfolio purposes. The company name and financial records used in the dataset are synthetic and do not represent the financial position of any real organization.

---

**Data becomes valuable when it leads to better decisions.**
