# Retail Data Pipeline, Cleaning & Dimensional Modeling

An end-to-end data cleaning and engineering project designed for **EXL**. This project transforms raw, transactional e-commerce data into a production-ready Star Schema optimized for downstream business intelligence and analytics.

---

## 📁 Repository Structure

```text
├── raw_data/                           # Original, unchanged transactional files
│   ├── orders.csv
│   ├── order_items.csv
│   ├── products.csv
│   └── users.csv
├── Cleaned_data/                       # Standardized and cleaned datasets
│   ├── orders_cleaned.csv
│   ├── order_items_cleaned.csv
│   ├── products_cleaned.csv
│   └── users_cleaned.csv
├── schemas/                            # Analytical Warehouse Layer (Star Schema)
│   ├── fact_orders.csv                 # Central metrics table (quantities, keys, sales)
│   ├── dim_users.csv                   # Customer dimension data
│   ├── dim_products.csv                # Product catalog dimension data
│   └── dim_date.csv                    # Custom time intelligence attributes
├── MiniProjectForEXL.ipynb             # Core Google Colab Python/Pandas cleaning script
├── Data Quality & Analyst Report.pdf    # Executive summary & data insight findings
└── star_schema_diagram.png             # Visual entity-relationship (ER) architecture map
```

---

## 📐 Data Architecture (Star Schema)

The core architecture separates operational data from analytical data by creating an optimized **Star Schema** to significantly reduce SQL `JOIN` complexities:

1. **Central Fact Table (`fact_orders.csv`)**: Holds transaction metrics, operational metrics, and foreign key pointers.
2. **Dimension Tables**:
   * **`dim_users.csv`**: Contains cleaned customer demographic profiles.
   * **`dim_products.csv`**: Organizes product metadata and category levels.
   * **`dim_date.csv`**: Designed explicitly to enable smooth time-series analytics (e.g., Month-over-Month growth tracking).

---

## 🛠️ Data Engineering & Pipeline Workflow

Executed inside the **`MiniProjectForEXL.ipynb`** notebook:

*   **Data Type Validation**: Cast system strings (like `amount`) to explicit floats and normalized timestamps to clean date values.
*   **Duplicate Elimination**: Scrubbed identical primary keys across transactional files to protect metric aggregates.
*   **Missing Value Strategy**: Handled null columns safely using targeted data profiling rules without discarding transactional context.
*   **Dimensional Conversion**: Re-architected raw operational rows into explicit relational fact and dimension tables.

---

## 📊 Deliverables Included
*   **Python Execution**: Complete data wrangling steps documented inside `MiniProjectForEXL.ipynb`.
*   **Documentation**: Comprehensive visual diagram mapping relationships stored in `star_schema_diagram.png`.
*   **Business Intelligence**: Deep-dive findings, exceptions, and metrics compiled inside the `Data Quality & Analyst Report.pdf`.

---
**Tech Stack:** Python, Pandas, Google Colab, Jupyter Notebooks, Git.
