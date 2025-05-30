## Overview
---
This case study answered relevant business questions about revenue and profit performance over five months across different states, product lines, product categories, sales teams, and stores with MySQL. In the project, I explored order distributions across different sales channels and identified high-performing products, the most profitable product categories, and the most profitable regions, as well as MoM growth, to offer insights and recommendations with the potential to guide investment strategies, marketing campaigns to drive sales, and training for sales teams to generate more revenue.

---


## Dataset Structure
The database consists of four tables:

sales_data

product

store_location

sales_team

---


### Data Preprocessing

To ensure accurate time-series and trend analysis, data preprocessing was carried out to convert the `sales_date` column—which was originally stored as a string in the format `dd/mm/yyyy`—into a proper `DATE` format. This process involved several steps:

1. **Date Conversion**: A new column was created to store the properly formatted date values. The string-formatted dates were converted using SQL’s `STR_TO_DATE()` function.
2. **Column Replacement**: The original `sales_date` column (string) was dropped, and the newly formatted date column was renamed to `sales_date`.
3. **Column Reordering**: The `sales_date` column was repositioned to follow immediately after the `order_number` column, maintaining logical consistency and improving data readability.

This preprocessing step was crucial for enabling chronological analyses such as monthly revenue trends, growth rates, and other time-dependent metrics.




### Calculated Fields for Sales Price and Profit

To enrich the dataset and facilitate meaningful analysis, two important calculated fields were added:

1. **Sales Price**:  
   A new column, `sales_price`, was introduced to represent the total revenue generated per transaction. It was computed as:  
   `sales_price = order_quantity * unit_price`

2. **Profit**:  
   Another column, `profit`, was created to reflect the net gain from each transaction. It was calculated using the formula:  
   `profit = sales_price - (order_quantity * unit_cost)`


These derived metrics were essential for conducting performance analysis across products, states, and sales representatives. By embedding them directly into the dataset, the need for repeated calculations in query operations was eliminated, improving efficiency and analytical clarity.

---

---
[Business Questions and Answers]().
