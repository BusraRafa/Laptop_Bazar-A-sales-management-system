
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

