# Power BI Sales Performance Analysis

## Project Overview

This project demonstrates how to build a business-ready Power BI dashboard using core analytics concepts such as time intelligence, iterators, and filter context.
It simulates a real-world sales reporting scenario, from data modeling to insight generation.

## Objectives

- Analyze sales trends over time

- Compare regional and product performance

- Apply advanced DAX concepts

- Build interactive, decision-ready dashboards

# 🗂 Dataset

File: Sales Analysis Report.xlsx

Key columns:

- Date

-City 

- Product Name

- Quantity

- Unit_Price

- Sales

The dataset represents daily sales transactions across cities and products.

## Data Architecure
![Sales_Performace](https://github.com/user-attachments/assets/62f080df-9935-4fb4-80e9-7d5c237fdb6e)


## 🧱 Data Model

- Created a dedicated Date table

- Established a one-to-many relationship between Date table and Sales table

- Marked Date table to enable time intelligence functions

## Key DAX Measures

### Total Sales

Total Sales =
SUM ( Sales[Sales] )

### Total Revenue (Iterator)
Total Revenue =
SUMX (
    Sales,
    Sales[Quantity] * Sales[Unit_Price]
)

### Sales Year-to-Date (YTD)

Sales YTD =
TOTALYTD (
    [Total Sales],
    DateTable[Date]
)

### Sales Last Year

Sales Last Year =
CALCULATE (
    [Total Sales],
    SAMEPERIODLASTYEAR ( DateTable[Date] )
)

### Region Contribution %
Region Contribution % =
DIVIDE (
    [Total Sales],
    CALCULATE (
        [Total Sales],
        ALL ( Sales[Region] )
    )
)

## 📈 Report Pages
### 1️⃣ Executive Overview

- KPI Cards (Total Sales, Sales YTD, Sales Last Year)

- Line chart for sales trend

- Region slicer

### 2️⃣ Regional Performance

- Bar chart comparing regions

- Table showing contribution percentages

- Product slicer

### 3️⃣ Product Analysis

- Matrix: Product vs Region revenue

- Bar chart of top products

## Concepts Demonstrated

- Time intelligence (YTD, prior period comparison)

- Iterators (SUMX)

- Filter context and context transition

## Data modeling best practices

Interactive dashboard design

## 🛠 Tools & Technologies

- Kaggle API

- Python 

- Power BI Desktop

- DAX

- xlsx dataset

- Data modeling & visualization

##  How to Run This Project
- Create a Kaggle account and generate an API
  
- Use python to extract the dataset
  
- Download the dataset

- Open Power BI Desktop

- Load the XLSX file

- Create the Date table and relationships

- Add the DAX measures

- Build visuals

# Key Takeaways

This project highlights how analytical thinking, DAX, and visualization come together to deliver business insights, not just charts.

# 📬 Contact

If you’re interested in learning Power BI, analytics, or data engineering through hands-on projects, feel free to connect.

# Author: Kindoli Edward
# Role: Data & Analytics Professional
