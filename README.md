# Bank Loan Analysis — Power BI Project

Turning raw loan data into a lending team's single source of truth.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Dashboard 1: Summary](#dashboard-1-summary)
3. [Dashboard 2: Overview](#dashboard-2-overview)
4. [Dashboard 3: Details](#dashboard-3-details)
5. [Getting Started](#getting-started)
6. [Dashboard Previews](#dashboard-previews)
7. [Contributing](#contributing)

---

## Project Overview

Bank leadership often lacks a single, consolidated view of how their loan portfolio is performing — how many applications are coming in, how much money is going out the door, how much is being repaid, and where risk is concentrated. Pulling this information manually from raw data every time it's needed is slow and error-prone.

This project solves that problem with a Power BI report built around three dashboards, each answering a different type of question:

- **Summary** — "What are the headline numbers right now?"
- **Overview** — "What trends and patterns exist across time, geography, and borrower segments?"
- **Details** — "Can I see the underlying, row-level data myself?"

Together, the three dashboards give stakeholders a complete picture of lending activity without needing to go back to raw data or SQL for routine questions.

---

## Dashboard 1: Summary

**Purpose:** Give leadership the headline KPIs at a glance, with enough granularity underneath to audit any number.

### Key Performance Indicators

The Summary dashboard tracks the following KPIs. Each one is calculated for the full reporting period, and also broken down into Month-to-Date (MTD) and Month-over-Month (MoM) views so trends and shifts are immediately visible.

| KPI | Description |
|---|---|
| Total Loan Applications | The total number of loan applications received during a specified period. Includes MTD totals and MoM change, so anyone viewing the report can see whether application volume is rising or falling relative to the previous month. |
| Total Funded Amount | The total amount of funds disbursed as loans. Tracked with MTD Total Funded Amount and MoM changes to monitor how lending volume is trending. |
| Total Amount Received | The total amount received back from borrowers, used to assess cash flow and loan repayment health. Includes MTD Total Amount Received and MoM changes. |
| Average Interest Rate | The average interest rate across all loans in the portfolio, along with MTD figures and MoM variation, to monitor pricing trends over time. |
| Average Debt-to-Income Ratio (DTI) | The average DTI across borrowers, giving a sense of how much financial strain the typical borrower is under. Calculated across all loans, MTD, with MoM fluctuations tracked. |

### Summary Visualization: Loan Status Grid

Beyond the KPI cards, the Summary dashboard includes a **Loan Status Grid** — a table view that breaks every one of the metrics above down by `Loan Status`. This gives viewers:

- Total Loan Applications by status
- Total Funded Amount by status
- Total Amount Received by status
- MTD Funded Amount by status
- MTD Amount Received by status
- Average Interest Rate by status
- Average DTI by status

This grid functions as an audit trail: if someone questions a headline number on the dashboard, they can immediately see which loan statuses are driving it.

---

## Dashboard 2: Overview

**Purpose:** Move beyond headline numbers into exploratory analysis — trends over time, geographic patterns, and borrower segment behavior.

Each visual on this dashboard was chosen deliberately to match the type of question it answers.

### 1. Monthly Trends by Issue Date — Line Chart

Plots lending activity over time based on the date each loan was issued. A line chart is used because the goal is to identify seasonality and long-term trends — patterns that are best read as a continuous progression rather than discrete categories.

### 2. Regional Analysis by State — Filled Map

Displays lending activity by U.S. state using a filled/choropleth map. This makes it possible to identify regions with significant lending activity and assess regional disparities — patterns that would be far harder to notice in a plain table.

### 3. Loan Term Analysis — Donut Chart

Shows the distribution of loans across different term lengths (for example, 36 months vs. 60 months). A donut chart works well here because there are only a couple of categories, and the goal is to understand proportion of the whole rather than a trend.

### 4. Employee Length Analysis — Bar Chart

Breaks down lending metrics by how long a borrower has been employed. A bar chart is used because there are many employment-length categories (from less than a year to 10+ years), and bars scale far better than a donut chart when comparing more than a handful of categories.

### 5. Loan Purpose Breakdown — Bar Chart

Provides a visual breakdown of loan metrics based on the stated purpose of each loan (for example, debt consolidation, car purchase, home improvement). Like the employment-length chart, bars make it easy to compare and sort many categories at once.

### 6. Home Ownership Analysis — Tree Map

Shows how home ownership status (rent, own, or mortgage) impacts loan applications and disbursements. A tree map is used because it communicates both hierarchy and relative magnitude at a glance, which suits this kind of proportional, categorical breakdown.

---

## Dashboard 3: Details

**Purpose:** Give analysts direct, filterable access to loan-level data without needing to query the underlying database.

### Objective

The Details dashboard provides a comprehensive view of key loan-related metrics and data points, giving users efficient access to critical information about loan portfolios, borrower profiles, and loan performance — all in one place.

### Dataset Fields Used

The dataset underlying this dashboard includes the following fields:

- Loan ID
- Address State
- Purpose
- Grade
- Sub Grade
- Annual Income
- Loan Status
- Last Payment Date
- Verification Status
- Debt-to-Income Ratio
- Interest Rates

Together, these fields provide insight into borrower demographics, employment stability, loan characteristics, risk assessment, and payment behavior.

### Why This Matters

The Details dashboard streamlines access to critical loan data. This supports:

- More informed decision-making
- Enhanced operational efficiency
- Optimized lending strategies
- Better risk mitigation
- Stronger overall portfolio performance

---

## Getting Started

Follow these steps to run the project locally.

### Step 1: Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/vinayak200227/Bank-Loan-Analysis-using-PowerBI.git
```

### Step 2: Open the Power BI Project

Open the `.pbix` file using Power BI Desktop.

### Step 3: Interact with the Dashboards

Explore the interactive dashboards and visualizations to gain insights into the bank loan data. Use the slicers and filters available on each page to narrow down the view to a specific state, purpose, grade, or time period.

---

## Dashboard Previews

Images of each dashboard can be found in the `Output` directory of this repository.

**Summary Dashboard**

`/Output/Summary.png`

**Overview Dashboard**

`/Output/Overview.png`

**Details Dashboard**

`/Output/Details.png`

---

## Contributing

Contributions to enhance the analysis or add new features are welcome. If you have any suggestions, ideas, or bug fixes, feel free to open an issue or submit a pull request.
