# ProhoOps-Real-Estate-Analytics
<img width="1376" height="654" alt="Screenshot 2026-06-08 012438" src="https://github.com/user-attachments/assets/906cfa90-2dfe-40a7-a198-bf402e9d2dfb" />
<img width="1375" height="650" alt="Screenshot 2026-06-08 012515" src="https://github.com/user-attachments/assets/ca4c8272-deb5-4f38-bc79-e151ed60dfdd" />

# ProhoOps: Real Estate Inventory & Channel Partner Analytics Dashboard

## 📌 Project Overview
This repository contains an end-to-end data analytics and business intelligence prototype designed to simulate the data infrastructure of **Prop.Guru**, an AI-driven Indian real estate technology and transaction advisory platform. 

The goal of this project was to transform raw, unstructured Indian residential property transaction data into an automated, relational data engine and an interactive executive-facing dashboard that monitors regional platform health, inventory liquidity, and partner networks.

---

## 🛠️ Tech Stack & Skills Demonstrated
*   **Advanced Excel:** Dynamic Lookup Architecture, Relational Data Modeling, Financial Margin Calculations.
*   **Data Engineering (SQL & Power Query):** Automated ET/Transform pipelines, Data Quality Audits, Null/Duplicate Resolution, Schema Mapping.
*   **Business Intelligence (BI):** Pivot Tables, Trend Visualizations, Multi-Chart Connected Slicers, UX Dashboard Design.

---

## 🏗️ Data Architecture & ETL Pipeline

### 1. Data Auditing & Cleaning (Power Query)
*   **Structural Integrity:** Evaluated schema sizing across thousands of raw transaction logs.
*   **Data Type Corrections:** Resolved text-to-integer anomalies hiding inside numerical columns (e.g., currency symbols and trailing spaces) to prevent analytical calculation errors.
*   **Deduplication & Null Resolution:** Isolated technical database glitches by eliminating identical duplicate records and resolving missing metrics via conditional validation logic.

### 2. Relational Database Modeling (Formulas Engine)
Real-world enterprise systems separate data tables to reduce memory footprints. To mirror this database architecture, I created distinct dimensional layers and connected them seamlessly using advanced formulas:
*   `XLOOKUP`: Dynamically mapped synthetic broker tracking IDs to official corporate names across the master transaction worksheet.
*   `VLOOKUP`: Handled vertical table scans to assign partner performance tiers.
*   `HLOOKUP`: Executed horizontal index scans across commission matrix tiers, implementing strict `FALSE` parameters to enforce exact matching parameters and prevent approximate data drift.

### 3. Financial Margin Optimization
*   Engineered conditional arithmetic columns to calculate precise transactional cuts.
*   Implemented logical `IF` parameters to isolate calculations strictly to properties successfully marked as **"Sold"**, preventing ongoing legal pipelines (`Pending`) or listings (`Available`) from distorting real-time corporate cash flows.
*   Created a Net Platform Revenue metric by calculating gross client transaction fees (3% baseline model) and subtracting operational broker payouts.

---

## 📊 Executive Dashboard Components
The final user layer features a clean visual data interface stripped of sheet clutter, configured with custom number formatting (Indian Rupees `₹` and precise percentages), and organized into three structural calculation streams:
1.  **Market Revenue Leaderboard (Pivot Table / Column Chart):** Ranks regional metropolitan hubs by true corporate net platform profits.
2.  **Channel Partner Commission Tracker (Pivot Table / Horizontal Bar Chart):** Tracks cash payouts drawn by the external broker network to analyze gross operational margins.
3.  **Resale Inventory Operations Funnel (Pivot Table / Donut Chart):** Monitors real-time pipeline liquidity by tracking the exact percentage of properties moving from active listings to legal closure.
4.  **Interactive Cross-Filtering (BHK Slicer):** Hardwired to all three independent visual charts via multi-table report connections, allowing executives to filter national metrics (e.g., 2 BHK vs. 3 BHK performance) with a single click.

---

## 🚀 How to Run the Project
1. Clone or download the `.xlsx` file from this repository.
2. Open the file in Microsoft Excel.
3. Navigate to the `Executive_Dashboard` tab to test the interactive `BHK` slicer controls.
4. Review the backend query architecture inside the `Master_Data_Sheet` and `Dashboard_Calculations` tabs to view the underlying lookup frameworks.
