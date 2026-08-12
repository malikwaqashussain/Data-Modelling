# 📐 Power BI Data Modeling Project

## Overview

A real-world **Data Modeling project in Power BI** focused on transforming a complex and highly connected dataset into a cleaner, scalable, and business-friendly semantic model.

The project demonstrates how proper data modeling can improve **report performance, DAX development, data accuracy, maintainability, and overall BI usability**.

The model was redesigned from a highly complex structure into a more organized architecture using **fact tables, dimension tables, a date dimension, and supporting bridge/fact tables**.

---

## Dashboard Overview
<img width="2559" height="1102" alt="project_data_modelling_dashboard" src="https://github.com/user-attachments/assets/4271b7c8-dbe3-4bb8-b5a6-0160292ab755" />

---

## Project Objective
<img width="1536" height="1962" alt="data_modelling_before_after" src="https://github.com/user-attachments/assets/3810f6be-85e2-45bb-8963-4fe347436a96" />

The main objective was to redesign the existing data model to:

* Simplify complex table relationships
* Separate business processes into appropriate fact tables
* Create reusable dimension tables
* Implement a scalable **Star Schema**
* Improve data model readability and maintainability
* Support accurate DAX calculations
* Improve Power BI report performance
* Enable secure reporting using **Row-Level Security (RLS)**

---

## 🔄 Before vs. After
![Uploading data_modelling_before_after.png…]()

### Before

The original model contained:

* Numerous interconnected tables
* Multiple relationship paths
* Repeated customer and product information
* Complex relationships between transactional tables
* Difficult-to-maintain structure
* Greater risk of ambiguous filtering and incorrect calculations

### After

The redesigned model follows a more structured architecture:

```text
                    dim_customer
                         |
                         |
dim_geo ---- fact_sales ---- dim_product
                         |
                         |
                     dim_date
```

Additional business processes were separated into dedicated fact tables such as:

* `fact_sales`
* `fact_inventory`
* `fact_campaign_spend`
* `fact_promotion_coverage`
* `fact_sales_target`
* `fact_order_process`

Supported by dimensions including:

* `dim_customer`
* `dim_product`
* `dim_date`
* `dim_geo`
* `dim_campaign`
* `dim_orders_flag`

This approach creates a clearer **semantic layer** between raw data and business reporting.

---

## ⭐ Key Data Modeling Principles Applied

### 1. Define the Business Process

Before modeling, I focused on understanding what each table represented and how the underlying business processes worked.

### 2. Define Table Grain

The grain of each fact table was identified before creating relationships and DAX measures.

For example:

```text
fact_sales
→ Sales transaction / line-level grain

fact_inventory
→ Product-level inventory by month

fact_campaign_spend
→ Campaign performance by date

fact_sales_target
→ Sales target by date
```

Defining grain helped prevent incorrect aggregations and duplicated values.

---

### 3. Star Schema

The model was redesigned around **fact and dimension tables** wherever possible.

```text
Dimensions
    ↓
Fact Tables
    ↓
Business Metrics
    ↓
Power BI Reports
```

This makes the model easier to understand and generally provides a better foundation for analytical reporting.

---

### 4. Fact & Dimension Separation

Transactional/business-process data was separated from descriptive attributes.

**Fact tables** contain measurable business events such as:

* Sales
* Inventory
* Campaign spend
* Sales targets
* Order processing

**Dimension tables** provide descriptive context such as:

* Customers
* Products
* Geography
* Dates
* Campaigns

---

## 🗓️ Date Dimension

A dedicated `dim_date` table was implemented with fields such as:

* Date
* Month
* Quarter
* Year

This provides a consistent foundation for:

* Monthly analysis
* Quarterly reporting
* Yearly comparisons
* Time intelligence
* Target vs. actual analysis

---

## 🔗 Relationships & Cardinality

The model required careful consideration of:

* One-to-many relationships
* Many-to-many relationships
* Filter direction
* Relationship paths
* Active and inactive relationships
* Dimension-to-fact relationships

The goal was to avoid unnecessary bidirectional relationships and ambiguous filtering.

---

## 🧮 DAX & Measures

A dedicated `_measure` table was created to keep business measures organized rather than scattering measures throughout the model.

Examples include:

```text
total_orders
total_sales
```

The model also supports advanced DAX concepts such as:

* `CALCULATE()`
* `SUM()`
* `SUMX()`
* `DIVIDE()`
* `USERELATIONSHIP()`
* Time intelligence

---

## 🔐 Row-Level Security

The model also incorporates an RLS structure using a security table containing:

```text
region
user_email
```

This allows the same Power BI model to serve different users while restricting the data they can access based on their assigned region or user identity.

---

## ⚡ Performance & Maintainability

Several modeling principles were applied to create a more efficient model:

* Removed unnecessary columns
* Reduced redundant data
* Used appropriate dimensions
* Organized measures separately
* Reduced unnecessary relationship complexity
* Applied consistent naming conventions
* Separated different business processes into appropriate fact tables

A clean model makes it easier to develop reports, troubleshoot calculations, and scale the solution as business requirements grow.

---

## 🛠️ Tools & Technologies

* **Microsoft Power BI**
* **Power Query**
* **DAX**
* **Data Modeling**
* **Star Schema**
* **Dimensional Modeling**
* **Row-Level Security (RLS)**
* **Power BI Semantic Models**

---

## 📊 Business Processes Modeled

The model brings together multiple business processes, including:

| Business Process   | Fact Table                |
| ------------------ | ------------------------- |
| Sales              | `fact_sales`              |
| Inventory          | `fact_inventory`          |
| Campaign Spend     | `fact_campaign_spend`     |
| Promotion Coverage | `fact_promotion_coverage` |
| Sales Targets      | `fact_sales_target`       |
| Order Processing   | `fact_order_process`      |

This allows multiple business processes to be analyzed through shared dimensions.

---

## 💡 Key Learning

The biggest lesson from this project was:

> **A Power BI dashboard is only as good as the data model behind it.**

Data modeling isn't simply about connecting tables.

It's about creating a **semantic layer** that ensures:

**Raw Data → Structured Model → Accurate Measures → Reliable Insights**

A well-designed model makes Power BI reports easier to build, faster to maintain, and more trustworthy.

---

## 📸 Project Screenshots

### Data Model — Before vs. After

![Before and After Data Model](data_modelling_before_after.png)

### Power BI Report / Model

![Power BI Data Modeling Project](project_data_modelling_dashboard.png)

---

## 📁 Suggested Repository Structure

```text
powerbi-data-modeling-project/
│
├── README.md
│
├── dashboard/
│   └── Data_Modeling_Project.pbix
│
├── screenshots/
│   ├── data-model-before-after.png
│   └── powerbi-data-model.png
│
└── documentation/
    └── modeling-notes.md
```

---

## 🚀 Skills Demonstrated

This project demonstrates practical experience in:

* Data Modeling
* Dimensional Modeling
* Star Schema Design
* Fact & Dimension Design
* Relationship Management
* DAX
* Power Query
* Power BI
* Semantic Layer Design
* RLS
* BI Performance Optimization
* Data Quality & Validation
* Business Intelligence

---

## 👤 Author

**Waqas Hussain**
**Business Intelligence & Data Analyst**

Focused on **Data Analytics, Business Intelligence, Power BI, SQL, and solving business problems by data**.
