# 📊 Regional UPI Transaction Analytics Dashboard

An interactive **Power BI dashboard** built to analyze and visualize **UPI transaction trends across regions**, providing insights into transaction volume, value, growth patterns, and user behavior.

## 🚀 Key Highlights

* 📈 Track overall UPI transaction performance
* 🌍 Analyze regional transaction distribution
* 💰 Monitor transaction value and volume trends
* 📊 Compare performance across multiple regions
* 🔍 Identify growth patterns and transaction insights
* 📅 Interactive time-based analysis with filters
* 🎯 Multi-page dashboard for detailed exploration

## 🛠️ Tools & Technologies

* **Power BI**
* **Excel / CSV Data Sources**
* **Data Cleaning & Transformation**
* **DAX Measures & Calculations**
* **Interactive Visualizations**

## 📌 Dashboard Features

* Executive Summary
* Regional Performance Analysis
* Transaction Trend Analysis
* Volume & Value Breakdown
* Dynamic Filters and Drill-Downs

## 📂 Repository Contents

* `Regional_UPI_Transaction_Analytics.pbix` – Power BI Dashboard File
* `README.md` – Project Documentation
* Dashboard PDF
* Dataset used zip file

## 📊 KPI Measures (DAX)

The following DAX measures were created to track key business metrics and monitor transaction performance.

| S.No | KPI | DAX Formula |
|------|-----|-------------|
| 1 | Total Transactions | `COUNT(Transactions[transaction id])` |
| 2 | Total Amount | `SUM(Transactions[amount (INR)])` |
| 3 | Successful Transactions | `CALCULATE([Total Transactions], Transactions[transaction_status] = "SUCCESS")` |
| 4 | Success Rate % | `DIVIDE([Successful Transactions], [Total Transactions])` |
| 5 | Fraud Transactions | `CALCULATE([Total Transactions], Transactions[fraud_flag] = 1)` |
| 6 | Fraud Rate % | `DIVIDE([Fraud Transactions], [Total Transactions])` |

---

### 🔹 Total Transactions

```DAX
Total Transactions =
COUNT(Transactions[transaction id])
```

**Purpose:** Calculates the total number of transactions processed.

### 🔹 Total Amount

```DAX
Total Amount =
SUM(Transactions[amount (INR)])
```

**Purpose:** Calculates the total transaction value in INR.

### 🔹 Successful Transactions

```DAX
Successful Transactions =
CALCULATE(
    [Total Transactions],
    Transactions[transaction_status] = "SUCCESS"
)
```

**Purpose:** Counts all successful transactions.

### 🔹 Success Rate %

```DAX
Success Rate % =
DIVIDE(
    [Successful Transactions],
    [Total Transactions]
)
```

**Purpose:** Measures the percentage of successful transactions.

### 🔹 Fraud Transactions

```DAX
Fraud Transactions =
CALCULATE(
    [Total Transactions],
    Transactions[fraud_flag] = 1
)
```

**Purpose:** Counts transactions flagged as fraudulent.

### 🔹 Fraud Rate %

```DAX
Fraud Rate % =
DIVIDE(
    [Fraud Transactions],
    [Total Transactions]
)
```

**Purpose:** Calculates the percentage of fraudulent transactions.

---

## 📈 Business Value

These KPIs help monitor:

- 💰 Total transaction volume and value
- ✅ Payment success performance
- 🚨 Fraud detection and risk monitoring
- 📊 Operational efficiency
- 📈 Digital payment adoption trends
  
---  

## 📅 Date Table - Calculated Columns

The following calculated columns were created using DAX to support time-based analysis and reporting.

| Column Created | DAX Formula |
|---------------|-------------|
| Year | `YEAR('Date'[Date])` |
| Month | `MONTH('Date'[Date])` |
| MonthName | `FORMAT('Date'[Date], "MMMM")` |
| DayName | `FORMAT('Date'[Date], "dddd")` |
| IsWeekend | `IF(WEEKDAY('Date'[Date]) > 5, 1, 0)` |

---

### 📌 Purpose of Each Column

| Column | Description |
|---------|------------|
| Year | Extracts the year from the date. |
| Month | Extracts the month number (1–12). |
| MonthName | Returns the full month name (January, February, etc.). |
| DayName | Returns the day name (Monday, Tuesday, etc.). |
| IsWeekend | Flags weekends with 1 and weekdays with 0. |

### 💡 Business Use Cases

- Year-wise trend analysis
- Month-wise transaction analysis
- Weekday vs Weekend transaction comparison
- Time-based filtering and drill-downs
- Seasonal pattern identification

## 🎯 Project Objective

To transform raw UPI transaction data into actionable business insights through interactive visualizations and analytics, enabling data-driven decision making.

---

⭐ If you found this project useful, consider giving it a star!
