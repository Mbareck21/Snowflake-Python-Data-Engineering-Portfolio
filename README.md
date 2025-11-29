# Snowflake & Python Data Engineering Portfolio ❄️ 🐍

This repository documents my journey building end-to-end Data Engineering pipelines. It demonstrates the integration of **Python (Pandas)**, **Snowflake (Data Warehousing)**, and **Power BI (Analytics)** to explore real-world business data.

## 🏆 Featured Project: Retail Sales ETL Pipeline

**Objective:** Engineer an automated pipeline to process government liquor sales data and visualize Year-Over-Year revenue growth.

### 📊 The Data
*   **Source:** [Montgomery County Warehouse and Retail Sales](https://catalog.data.gov/dataset/warehouse-and-retail-sales) (via Data.gov).
*   **Description:** A transactional dataset tracking alcohol sales from the Montgomery County (Maryland) Department of Liquor Control to retail licensees.
*   **Volume:** ~300,000+ rows of historical sales data.
*   **Key Metrics:** `Retail Sales ($)`, `Warehouse Sales ($)`, `Item Type` (Wine, Beer, Liquor), and `Supplier`.

### 1. The Architecture
*   **Extract:** Python script ingests raw CSV data from local storage.
*   **Transform:** Pandas performs data cleaning, header standardization (Snake Case), and historical filtering to optimize dataset size.
*   **Load:** Utilizes `snowflake.connector` and the optimized `write_pandas` API to bulk load data into the Snowflake Cloud Data Warehouse.
*   **Visualize:** Power BI connects directly to Snowflake to model a Star Schema and render interactive dashboards.

### 2. The Code (`Retail_Sales_ETL.ipynb`)
The Python script demonstrates:
*   **Dynamic transformations:** `[c.upper().replace(' ', '_') for c in df.columns]`
*   **Cloud Connectivity:** Secure connection using Snowflake credentials.
*   **Bulk Loading:** Efficient data transfer avoiding row-by-row insertion.

### 3. The Dashboard
*   **Time Intelligence:** DAX measures calculated for **Sales Last Year** and **YoY Growth %**.
*   **Drill Down:** Transaction-level date hierarchy logic implemented in Power Query.

![Power BI Dashboard](https://github.com/Mbareck21/Snowflake-Python-Data-Engineering-Portfolio/blob/main/Images/power_bi_dashboard.png)

---

## 📂 Another Project Related to this Repo [Snowflake](https://github.com/Mbareck21/Snowflake)

| File | Skillset | Description |
| :--- | :--- | :--- |
| `CDCPipeline.sql` | **Automation (CDC)** | A "Set it and Forget it" pipeline using Snowflake **Streams & Tasks** to ingest JSON data in real-time. |
| `JSONParsing.sql` | **Semi-Structured Data** | Parsing complex nested JSON logs using `VARIANT` and `FLATTEN` to handle schema drift. |
| `PowerBIPrep.sql` | **Data Modeling** | Building a **Star Schema** (Fact/Dimension tables) and creating secure Views for VIP reporting. |
| `Optimization.sql` | **Query Tuning** | Demonstrating **Partition Pruning** to reduce query costs by 90% using effective WHERE clauses. |

---

## 🛠️ Technical Skills Demonstrated
*   **Languages:** Python, SQL (Snowflake Dialect), DAX.


## 👤 Author
**Mohamed Lemine Mbareck**
*   [LinkedIn Profile](https://www.linkedin.com/in/lemine-mbareck/)
*   [Portfolio Website](https://portfolio-drab-nine-66.vercel.app/)
