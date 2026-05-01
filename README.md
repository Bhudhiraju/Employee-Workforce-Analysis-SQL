Employee Workforce Analysis — SQL + Excel Dashboard Project
Project Overview
This end-to-end analytics project analyzes employee workforce data across 5 departments using MySQL for data cleaning and analysis, and Microsoft Excel for dashboard visualization. The goal was to uncover productivity patterns, attendance trends, manager performance gaps, and department-level insights to support HR and operations decision-making.

Tools Used
MySQL Workbench — Data cleaning, exploration, joins, window functions
Microsoft Excel — Pivot tables, charts, KPI dashboard
GitHub — Version control and portfolio hosting


Dataset Description
Source: Custom workforce dataset simulating real operations data
Raw Records: 579 rows
Clean Records: 536 rows (after removing NULLs and duplicates via SQL)
Tables:

workforce_data — Employee level records including attendance, shift, productivity units
dept_targets — Department level monthly targets, team size, manager details


Columns: Employee_ID, Employee_Name, Department, Shift, Manager, Actual_Units, Target_Units, Attendance_Status, Monthly_Target_Units


Project Structure
Employee-Workforce-Analysis/
│
├── Employee_Workforce_Dashboard.xlsx   # Excel dashboard with pivot tables and charts
├── Workforce_SQL_Queries.sql           # All 15 SQL queries with comments and findings
└── README.md                           # Project documentation

SQL Analysis — 15 Questions

Section A: Data Cleaning & Exploration
Q#QuestionKey Finding Q1Find records where Target_Units or Actual_Units is NULL2 records flagged — 1 Missing Actual, 1 Both Missing Q2Find duplicate records (same Employee_ID + Work_Date)14 duplicate combinations found Q3Count records per Department variant7 variants found — Ops, H.R., finance are dirty Q4Standardise Department column using CASE WHEN579 rows returned with clean department labels Q5Employee achievement % — flag those below 80%0 rows — no employee has sustained underperformance Q6Department with highest average productivity gapAll gaps negative — Actual exceeds Target across all depts Q7Employees with 3+ records of underperformance + poor attendance26 employees flagged as HR risk Q8Employees below company-wide average Actual_Units22 employees identified for coaching

Section B: Joins, Targets & Performance Analysis
Q9 Join workforce_data with dept_targets579 rows returned after join Q10 Find unmatched department variants using LEFT JOINH.R. and Ops confirmed as unmatched dirty variants Q11 Department performance vs monthly targetAll 5 departments exceeding — targets need revision

Section C: Shift, Attendance & Manager Analysis

Q12 Shift with highest average Actual_UnitsEvening (74.83) > Night (73.55) > Morning (70.20)Q13Attendance rate per departmentOperations leads (35.38%), HR is lowest (26.58%) Q14 Manager with most underperforming recordsMeghana T highest rate (45.93%), Anil K lowest (39.69%)Q15Top performer per departmentHR — Revathi Kumar (116), IT — Aditya Nair (114)

Excel Dashboard
                           KPI Cards
                           KPI Value 
Total Records 536       Cumulative Achievement %554%  Overall Attendance Rate 31.57%     Highest Performing Department   IT

Charts

Manager Underperformance Rate % — Horizontal bar showing underperformance rate per manager
Department Performance vs Monthly Target — Clustered column comparing actual vs target per department
Average Productivity by Department — Horizontal bar showing average actual units per department
Shift Productivity Comparison — Horizontal bar comparing productivity across Evening, Night, Morning shifts
Attendance Rate % by Department — Horizontal bar showing present rate per department


Key Findings

All 5 departments exceed monthly targets with an overall cumulative achievement of 554% — targets need upward revision for the next cycle
IT leads performance at 687% achievement with 10,310 actual units against a 1,500 target
Operations achieves 431% — lowest achievement rate despite having the largest monthly target
Overall attendance is critically low at 31.57% — fewer than 1 in 3 employees present on any given day
Operations leads attendance at 35.38% while HR has the worst at 26.58% — HR manages workforce yet shows lowest presence
Meghana T has the highest team underperformance rate at 45.93% — Anil K is the most consistent manager at 39.69%
All 4 managers have underperformance rates above 39% — confirms a company wide performance gap not isolated to one team
Evening shift is most productive at 74.83 average units vs Morning at 70.20 — shift scheduling review recommended
Sales is a dual concern department — lowest productivity (71.27) and second lowest attendance (29.79%)
Top performers: Revathi Kumar HR (116), Aditya Nair IT (114), Karthik Nair Operations (110) — retention critical


Skills Demonstrated

Data cleaning using CASE WHEN, LOWER(), IS NULL, HAVING
Joins — INNER JOIN, LEFT JOIN with complex ON conditions
Window functions — RANK() OVER (PARTITION BY)
Aggregations — SUM, AVG, COUNT, conditional SUM
Subqueries and CTEs
Excel PivotTables and PivotCharts
Dashboard design and KPI reporting
Business insight generation from data


Author
Harika | Operations to Data Analytics Transition
Targeting: Data Analyst | Business Intelligence Analyst| Operations Data Analyst
Location: Hyderabad, India
