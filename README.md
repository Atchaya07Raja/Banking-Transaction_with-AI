# Banking-Transaction_with-AI
End-to-end banking analytics project using SQL for data cleaning and Power BI for interactive dashboards, featuring AI-generated synthetic data and custom DAX KPIs.

SQL + Power BI Banking Dashboard with AI-driven DAX KPIs

# Banking Transactions Data Cleaning & Visualization  

## 📌 Project Overview  
This project showcases an **end-to-end data analytics process** using **SQL**, **Power BI**, and **DAX** to transform raw, unclean synthetic banking data into meaningful insights.  

The dataset was generated using **Perplexity AI** and contains:  
- **10,000 dummy transactions**  
- **Customers** table  
- **Accounts** table  

The data was deliberately designed with **null values, errors, and duplicates** to mimic real-world banking data challenges.  

---

## 🔄 Workflow Steps  

### 1️⃣ Data Generation  
- Created three relational tables:  
  - **Customers**: ID, personal details, demographics  
  - **Accounts**: Account details, type, balances  
  - **Transactions**: Transaction ID, account linkage, amount, type, date  
- Introduced missing data, duplicate records, and inconsistent formats.  

### 2️⃣ Data Cleaning & Preparation (SQL)  
- Removed duplicate rows.  
- Handled null values via deletion or imputation.  
- Corrected data types and formatting.  
- Enforced referential integrity between tables.  
- **Used `LEFT JOIN`** to merge **Customers**, **Accounts**, and **Transactions** tables — ensuring all customer/account records were retained even if transactions were missing.  
- Created cleaned, analysis-ready tables for Power BI import.  

### 3️⃣ Data Visualization (Power BI)  
- Imported cleaned data into **Power BI**.  
- Created interactive dashboards to explore:  
  - Transaction trends  
  - Account balances  
  - Customer demographics  
- Applied **DAX measures** generated with AI for KPI tracking.  

---

## 📊 KPIs & DAX Measures  

| KPI | Description | Visual | DAX / Example |
|-----|-------------|--------|---------------|
| Transactions by Type | Count of transactions grouped by type | Pie Chart / Stacked Column | `COUNT(CombinedBankingDataset[TransactionID])` grouped by `TransactionType` |
| Monthly Transaction Amount | Total transaction amount by month | Line / Area Chart | `Monthly Transaction Amount = CALCULATE(SUM(CombinedBankingDataset[TransactionAmount]), MONTH(CombinedBankingDataset[TransactionDate]))` |
| Top N Customers by Transaction Value | Customers with the highest transaction values | Top N Bar Chart | Apply **Top N** filter on `CustomerName` by SUM(TransactionAmount) |
| Total Balance by Account Type | Total balance per account type | Clustered Bar | `Total Balance = SUM(CombinedBankingDataset[Balance])` grouped by `AccountType` |
| Monthly Transaction Balance by Month | Net balance trends across months | Line / Area Chart | `Monthly Transaction Balance = CALCULATE(SUM(CombinedBankingDataset[Balance]), MONTH(CombinedBankingDataset[TransactionDate]))` |
| Customer Count by Gender | Distribution of customers by gender | Donut Chart | `Customer Count = COUNTROWS(VALUES(CombinedBankingDataset[CustomerID]))` grouped by `Gender` |

---

## 📷 Dashboard Previews  

### Page 1 – Transaction Trends & Account Insights  
![Page 1 Dashboard]<img width="1920" height="1080" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/8f8e8661-72ee-4ee4-8fd0-4ad5ff00bdd3" />
 

### Page 2 – Customer & Account Demographics  
![Page 2 Dashboard]<img width="1920" height="1080" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/144765be-9c9e-4fe7-8121-3e842e3dee56" />
 

---

## 📌 Insights  

From the analysis:  
- Certain account types dominate the total balance share.  
- Monthly transaction volumes show seasonal fluctuations, with peaks in **June** and **December**.  
- A small number of customers contribute disproportionately to total transaction value.  
- Inactive accounts are clustered in specific months, potentially due to customer churn or inactivity.  
- Gender and age group distributions reveal concentrated demographics.  

---

## 🏁 Conclusion  

This project highlights how **AI-generated synthetic data** can be used for **practical data analytics exercises**.  
It demonstrates:  
- **SQL proficiency**, including the use of **`LEFT JOIN`** for combining datasets while preserving all base records.  
- **Power BI dashboarding** for visual storytelling.  
- **DAX measure creation** for KPI insights.  

The workflow mirrors a real-world **ETL pipeline** — from raw, messy data to interactive reports that inform decision-making.  

---

## 🛠 Tools Used  
- **SQL** – Data cleaning, transformation, `LEFT JOIN` merging, and validation  
- **Power BI** – Visualization and dashboard creation  
- **DAX** – Custom measures and KPI calculation  
- **Perplexity AI** – Synthetic dataset generation  

---

## 📜 License  
This project uses **synthetic data** and is intended for **educational and demonstration purposes only**. 
