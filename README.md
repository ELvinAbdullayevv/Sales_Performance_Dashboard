**Sales_Performance_Dashboard**

**Project Overview**
This project focuses on analyzing sales performance using Power BI. The dashboard provides key insights into actual vs. expected sales, sales trends over time, and differences in performance across countries. The aim is to visualize business-critical metrics and help stakeholders make data-driven decisions.

**Project Objectives**
•	Analyze actual vs. expected sales per country
•	Provide a KPI metric to measure sales performance differences
•	Visualize cumulative sales trends over time
•	Enable time-based filtering with a Period Slicer
•	Ensure stakeholder usability through an interactive and structured layout


**Tools & Technologies Used**
•	Power BI – For building interactive reports & dashboards 
•	DAX (Data Analysis Expressions) – For custom calculations & KPIs 
•	Excel (.xlsx dataset) – Data source for sales analysis


**Key Features & Visualizations**

**1) Sales by Country (Table Visual)**
•	Displays actual vs. expected sales 
•	Includes difference % calculation 
•	Helps in identifying performance gaps across countries

**2) KPI Visual – Sales Difference %**
•	Highlights overall % difference between actual and expected sales 
•	Uses DAX calculations to dynamically update values 
•	Helps track business performance at a glance

**3) Cumulative Sales Over Time (Line Chart)**
•	Shows running total of actual sales over time 
•	Helps in trend analysis and identifying seasonal fluctuations

**4) Time-Based Filtering (Period Slicer)**
•	Allows users to filter data by Month & Year 
•	Helps analyze sales performance for specific periods

**5) Reserved Space (For Future Business Requirements)**
•	Placeholder for potential additional metrics or insights


**Step-by-Step Implementation**

**Step 1: Data Preparation**
•	Loaded the Financial Sample dataset into Power BI
•	Cleaned and structured the data for analysis
•	Merged Actual Sales & Expected Sales for comparison

**Step 2: Creating Key Measures (DAX Calculations)**
**Difference Percentage Calculation (KPI)**
Difference Percentage = 
VAR Diff = 
    IF(
        AND(
            NOT(ISBLANK(SUM(Actuals[Actual Sales]))),
            NOT(ISBLANK(SUM(Actuals[Expected Sales])))
        ),
        (SUM(Actuals[Actual Sales]) / SUM(Actuals[Expected Sales])) - 1,
        BLANK()
    )
RETURN 
    FORMAT(Diff, "0.0%")

**Running Total for Actual Sales**
RunningTotalSales = 
CALCULATE(
    SUM(Actuals[Actual Sales]),
    FILTER(
        ALLSELECTED(Actuals),
        Actuals[YearMonthNumber] <= MAX(Actuals[YearMonthNumber])
    )
)


**Step 3: Building the Visualizations**

•	Created a Table visual for Actual vs. Expected Sales
•	Designed a KPI visual to display the percentage difference
•	Built a Line Chart for cumulative sales trends
•	Added a Time Slicer to filter by Month & Year
•	Reserved a section for future business needs

**Step 4: Formatting & Optimization**

•	Applied conditional formatting to highlight performance differences
•	Ensured responsive design for better user experience
•	Used clear titles & tooltips to improve readability

![image](https://github.com/user-attachments/assets/8691d700-dae2-4613-8984-a7eef8056e5d)












