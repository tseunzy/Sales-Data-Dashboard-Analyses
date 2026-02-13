

# Sales Dashboard (Jupyter Analytics)


# Overview

    This project is a sales analytics dashboard built inside a Jupyter Notebook to help managers quickly understand business performance. It cleans raw sales data, computes key KPIs, analyzes performance across major business dimensions, and visualizes trends using clear charts.

    The focus is on producing results that are easy to interpret and ready to export for reporting.


# Objectives

    - Prepare and standardize sales data for analysis
    - Track core sales KPIs such as Revenue, Orders, Quantity, AOV, and Profit
    - Identify top performers and underperformers acrossmonths, products, categories, regions, and salespeople
    - Visualize sales trends and revenue concentration clearly for decision-making
    - Export cleaned data, summary tables, and charts for managers


# KPI Definitions

    - Revenue: Total sales value (computed as Quantity × UnitPrice if not provided)
    - Total Orders: Number of unique orders (based on OrderID, if available)
    - Quantity Sold: Total number of items sold
    - AOV (Average Order Value): Revenue / Total Orders (if OrderID exists)
    - Average Selling Price: Revenue / Quantity Sold
    - Profit: Revenue − Cost (if Cost exists) or from provided Profit column


# Dataset Expectations

    The notebook is designed to work with CSV or Excel files. It adapts if some columns are missing, but typical columns include:
    - Date
    - OrderID
    - Product
    - Category
    - Region
    - Salesperson
    - Quantity
    - UnitPrice
    - Discount
    - Cost
    - Revenue
    - Profit

# NOTE: TO-DO
    
    # you can add your uniques column spellings to matches the expected one in the code depending on how yours is been spelt. e.g Product as prodID

    date_col = find_column(df, ['Date'])
    product_col = find_column(df, ['Product','Product ID','Product_ID'])
    order_col = find_column(df, ['Order', 'Order', 'Purchase'])
    category_col = find_column(df, ['category', 'Category', 'Category Type'])
    region_col = find_column(df, ['region', 'Country', 'Region'])
    salesperson_col = find_column(df, ['Sales Person', 'Salesperson','Sales_Person'])
    quantity_col = find_column(df, ['Quantity', 'qty'])
    cost_col = find_column(df, ['Cost','Price','Amount', 'Cost_Price'])
    unitprice_col = find_column(df, ['PriceUnit', 'Price_Unit', 'UnitPrice', 'Unit_Price'])
    profit_col = find_column(df, ['Profit'])
    revenue_col = find_column(df, ['Revenue'])
    discounted_col = find_column(df, ['Discount', 'Discounted_Price', 'Discounted', 'Discount_Price'])



# Tools Used

    - Python
    - pandas for data cleaning and analysis  
    - numpy for calculations and feature engineering  
    - matplotlib for charts and visual reporting  
    - seaborn for optional styling and quick exploration  



# Steps

# Setup

    - Imports libraries
    - Sets pandas display options
    - Loads CSV or Excel data
    - Displays basic inspection: head, shape, info, column list

# Data Cleaning and Preparation

    - Removes duplicates
    - Converts date to datetime (if available)
    - Converts numeric fields safely (Quantity, UnitPrice, Revenue, Discount, Profit, Cost)
    - Standardizes key text columns (Product, Category, Region, Salesperson, Channel)
    - Builds missing fields possible:
    - Revenue = Quantity × UnitPrice (if Revenue is not provided)
    - Profit = Revenue − Cost (if Profit is missing but Cost exists)

# KPI Summary

    Calculates and displays a manager-friendly KPI snapshot:
    - Total Revenue
    - Total Orders (if OrderID exists)
    - Total Quantity Sold
    - AOV (if OrderID exists)
    - Average Selling Price
    - Total Profit
    - MoM and YoY growth tables (if Date exists)

# Core Business Analysis

    Produces summary tables for:
    - Revenue by Month
    - Top Products and Categories (Highest/Lowest)
    - Revenue by Region
    - Revenue by Salesperson

# Visualizations 

    Creates clean charts with labels and titles:
    - Line chart: Revenue over time (monthly)
    - Bar chart: Top 10  Highest/Lowest products by revenue
    - Bar chart: Revenue by region
    - Bar chart: Profit by category 

# Export Outputs

    Exports results for reporting:
    - Cleaned dataset (CSV)
    - Summary tables (Excel with multiple sheets)
    - Charts saved as PNG files


# Outputs

    After running the notebook, you will get files like:

    outputs_sales/
    - sales_cleaned.csv
    - sales_dashboard_tables.xlsx
    - revenue_overt_month.png
    - high_prod_revenue.png
    - low_prod_revenue.png
    - region_revenue.png
    - Revenueby_category.png
    - Profit_by_category
    - Revenueby_salesperson.png

# For my example i made use of profit as rev columnn thats the reason for the charts 