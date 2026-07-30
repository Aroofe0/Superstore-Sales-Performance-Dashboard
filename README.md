# 📊 Superstore Sales Performance & Dynamic Target Analysis

## 📌 Executive Summary
This project presents an interactive **Power BI Dashboard** built to analyze historical retail sales performance, optimize inventory/order tracking, and evaluate monthly performance against dynamic targets. The dashboard transitions raw transactional data into actionable business insights for stakeholders.

---

## 📸 Dashboard Overview
*(You can upload a screenshot of your overview page here)*

---

## 🎯 Business Problem & Key Insights
* **Target Tracking:** Implemented a dynamic monthly KPI target comparison. Months achieving sales growth over previous period targets are highlighted in green, while underperforming months trigger visual alerts.
* **Profitability vs. Volume:** Identified key product categories and regional segments where high sales volume did not translate to healthy profit margins due to excessive discounts.
* **Granular Time Intelligence:** Enabled interactive filtering across yearly and monthly granularity to prevent distorted comparisons across different time frames.

---

## 🛠️ Technical Stack & DAX Highlights
* **Tool:** Power BI Desktop
* **Data Modeling:** Star Schema design connecting Sales Fact Table with Calendar and Product Dimensions.
* **Key DAX Formulas:**
  * **Dynamic Target Calculation:**
    ```dax
    Targget = 
    CALCULATE(
        [Total Sales] * 1.10, 
        SAMEPERIODLASTYEAR('Calendar'[Date])
    )
    ```
  * **Conditional Formatting Indicator:**
    ```dax
    fx Target = 
    IF(
        ISBLANK([Total Sales]) || ISBLANK([Targget]),
        "#CCCCCC",
        IF([Total Sales] >= [Targget], "#2ECC71", "#E74C3C")
    )
    ```

---

## 📁 Repository Structure
* `Superstore_Dashboard.pbix` : Power BI main project file.
* `Data/` : Cleaned dataset files.
* `README.md` : Documentation.

---

## 👤 Author
Developed as part of an end-to-end Data Analytics Portfolio.
