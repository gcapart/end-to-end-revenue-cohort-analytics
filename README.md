# End-to-End Revenue & Cohort Analytics  
**SQL (PostgreSQL) + Power BI**

This project showcases a complete end-to-end analytics workflow, from building an analytical data layer in PostgreSQL to delivering executive-level dashboards in Power BI, using the public **Olist e-commerce dataset (Brazil)**.

The focus is on **Revenue Analytics, Customer Behavior, Retention and Repeat Purchase Analysis**, applying solid data modeling, metric design and visualization best practices.

---

## Project Objectives

- Build a reusable **analytical layer in PostgreSQL** from transactional e-commerce data.
- Design **SQL views optimized for BI consumption**.
- Analyze:
  - Revenue performance and time trends
  - Average Order Value (AOV)
  - Customer retention through cohort analysis
  - Repeat customers and revenue contribution
- Develop clean, business-oriented dashboards in **Power BI**.

---

## Tech Stack

- **PostgreSQL** — analytical data layer
- **SQL** — transformations and metrics
- **Power BI** — dashboards and reporting
- **DAX** — KPIs and calculated measures
- **DBeaver** — SQL exploration and validation

---

## Data Source

Public **Olist e-commerce dataset**:
- Customers
- Orders
- Order Items
- Products
- Sellers
- Product Category Translation

---

## Analytical Data Model (SQL Layer)

The project is built on a **view-based analytical layer**, designed to be directly consumed by Power BI.

### Core Views

- **`public.v_sales`**  
  Item-level sales view.  
  **Grain:** one row per order item.  
  Includes real customer identifier (`customer_unique_id`), prices, categories and purchase dates.

- **`public.v_kpis`**  
  Global commercial KPIs:
  - Revenue
  - Orders
  - Customers
  - Average Order Value (AOV)

- **`public.v_orders_unique`**  
  Unique orders per customer.  
  Used to prevent customer duplication in retention and repeat purchase analysis.

- **`public.v_cohort`**  
  Cohort base assigning each customer to a first-purchase month (`cohort_month`) and calculating the relative purchase month (`cohort_index`).

- **`public.v_retention`**  
  Monthly cohort retention metrics:
  - Active customers
  - Cohort size
  - Retention percentage  
  Ready to be visualized as a cohort matrix in Power BI.

---

## Power BI Dashboards

The Power BI file includes three main analytical pages:

### 1. Revenue Overview
- Revenue, Orders, Customers and AOV
- Revenue evolution by Year-Month
- Top product categories by revenue
- Interactive date filtering

### 2. Cohort & Retention Analysis
- Average M1 retention
- Retention curve by cohort index
- Cohort heatmap (retention %)
- Churn and customer lifecycle insights

### 3. Repeat Customers Analysis
- Total vs repeat customers
- Repeat rate
- Revenue share from repeat customers
- Orders per customer distribution
- Monthly evolution of repeat revenue share

---

## Repository Structure

├── sql/
│ ├── v_sales.sql
│ ├── v_kpis.sql
│ ├── v_orders_unique.sql
│ ├── v_cohort.sql
│ └── v_retention.sql
│
├── powerbi/
│ └── end_to_end_revenue_cohort_analytics.pbix
│
└── README.md


---

## How to Use

1. Restore or load the Olist dataset into PostgreSQL.
2. Create the SQL views included in the `sql/` folder.
3. Open the `.pbix` file in Power BI Desktop.
4. Connect Power BI to the PostgreSQL database.
5. Refresh and explore the dashboards.

---

## Project Scope

This project was developed as a **portfolio-grade analytics case**, focusing on:
- Realistic e-commerce business questions
- Clean analytical modeling
- SQL-first metric definition
- Business-oriented Power BI storytelling

---

## Author

**Gastón Capart**  
Data Analytics & Business Intelligence
