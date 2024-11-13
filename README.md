
# Laptop_Bazar – Sales Management System

## Overview

**Laptop_Bazar** is a sales management system developed in **PL/SQL** with an **Oracle Database** backend, leveraging **Distributed Database Links** for seamless data exchange. The system tracks laptop sales, identifies top-selling models, and highlights high-spending customers. It also offers recommendations based on laptop specifications.

## Key Features

- **Top-selling Laptops**: Identifies and lists the most popular laptops based on sales data.
- **Top Customers**: Retrieves and ranks customers by their total purchase amounts.
- **Laptop Recommendation**: Suggests laptops based on specifications like memory, storage, battery, and price using nearest neighbor logic.

## Technologies Used

- **PL/SQL**
- **Oracle Database**
- **Distributed Database Links**
- **Triggers and Procedures**
- **Views and Cursors**
## Global Schema
The global schema defines how the data is distributed and how tables are related across different sites. It includes the following key tables:

1. **Laptop (pid, brand, graphics, price, SID, BranchID)**
2. **Specification1 (pid, memory, storage, cpu_speed, battery, display)**
3. **Specification2 (pid, memory, storage, cpu_speed, battery, display)**
4. **Order_D (CID, pid, price)**
5. **Branch (BranchID, branch_name, location)**
6. **Customer (CID, name, contact_info)**
7. **Top_Selling (brand, popularity)**
8. **Seller_Sold (pid, seller_id, sold_count)**

## Fragmentation Schema

### Site 1
- **Laptop (pid, brand, graphics, price, SID, BranchID)**
- **Specification1 (pid, memory, storage, cpu_speed, battery, display)**
- **Top_Customer (CID, total_purchase)**
- **Top_Selling_Brand (brand, popularity)**
- **Seller_Sold (pid, seller_id, sold_count)**
- **View (view_id, brand, graphics, price, SID, BranchID)**

### Site 2
- **Specification2 (pid, memory, storage, cpu_speed, battery, display)**
- **Distance2 (pid, df_memory, df_storage, df_cpu_speed, df_battery, df_display)**
- **Prediction (pid, predicted_price, predicted_specs)**
- **Connection (site_link)**
- **Distance1 (pid, df_memory, df_storage, df_cpu_speed, df_battery, df_display)**

## Allocation Schema

### At Site 1:
- **Laptop**
- **Specification1**
- **Top_Customer**
- **Top_Selling_Brand**
- **Seller_Sold**
- **View**

### At Site 2:
- **Specification2**
- **Distance2**
- **Prediction**
- **Distance1**
- **Connection**


## File Descriptions

- **connection.sql**: Creates a database link to connect to another server for cross-database queries.
- **top_customer.sql**: Fetches and displays the top 5 customers by total purchase amount.
- **top_selling.sql**: Lists the most popular laptop brands based on sales data.
- **view.sql**: Creates views for laptop data and specifications from different sources.
- **distance.sql**: Creates a table to store laptop specification differences for recommendation calculations.
- **pakagesite1.sql**: Defines PL/SQL packages for laptop recommendation, including procedures for filtering by memory, storage, battery, and price.
- **specification1.sql**: Creates and populates the `specification1` table, storing laptop specifications.

## Setup Instructions

1. **Database Setup**: Import all SQL scripts into your Oracle Database.
2. **Establish Database Link**: Execute `connection.sql` to set up a database link for remote queries.
3. **Run SQL Scripts**: Execute the other SQL scripts (`top_customer.sql`, `top_selling.sql`, etc.) to create tables, views, and procedures.

## Usage

- Use the **top_customer.sql** to view the top 5 customers by total purchase.
- Use the **top_selling.sql** to list popular laptop brands.
- Use the **pakagesite1.sql** procedures to get laptop recommendations based on various specifications.

