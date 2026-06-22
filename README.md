Securitisation Risk Analytics & IFRS 9 ECL Dashboard
Project Overview

This project is a Power BI-based Securitisation Risk Analytics system designed to monitor loan portfolio performance, estimate credit risk, and support investor reporting.

It implements IFRS 9 Expected Credit Loss (ECL) framework along with advanced analytics like:

DPD Risk Analysis
Vintage Analysis
Waterfall & Tranche Modeling
Stress Testing
Investor Reporting Dashboard
Gamified Risk Arena

 Objective
Build an end-to-end credit risk analytics solution
Analyze loan delinquency and default behavior
Estimate Expected Credit Loss (ECL)
Simulate economic stress scenarios
Provide investor-level reporting dashboards

Business Problem

Financial institutions need to:

Track loan performance across DPD buckets
Predict expected credit losses (IFRS 9)
Monitor portfolio exposure and risk
Analyze cashflow distribution in securitisation
Evaluate performance under economic stress conditions

Dataset Description
Auto Loan Securitisation Data
Loan ID, Current Balance, Interest Rate, Default Status
DPD Snapshot History
Days Past Due, Snapshot Date, Bucket classification
Dynamic Loss Data
Default amount, recovery amount, net loss
Vintage Data
Origination date, cohort grouping, performance trends

Data Model
Star Schema Design
Fact Table: Auto Loan Portfolio
Dimension Tables:
DPD Snapshot
Vintage Table
Date Table

Relationships built using:

Loan ID
Date keys
Key DAX Measures
Total Exposure
Total Exposure = SUM(auto_loan_securitisation_data[CurrentBalance])
Probability of Default (PD)
PD =
DIVIDE(
SUMX(auto_loan_securitisation_data,
IF(auto_loan_securitisation_data[IsDefaulted]=TRUE(),1,0)
),
COUNT(auto_loan_securitisation_data[LoanID])
)
Expected Loss (IFRS 9)
Expected Loss = [PD] * 0.4 * [Total Exposure]
Net Cashflow
Net Cashflow = [Total Exposure] - [Expected Loss]

Dashboard Pages
Executive Dashboard
DPD Risk Analysis
IFRS 9 ECL Modeling
Vintage Analysis
Waterfall & Tranche Analysis
Stress Testing Framework
Investor Reporting Dashboard
Securitisation Risk Arena

Key Features
Loan-level risk monitoring
DPD bucket segmentation
IFRS 9 compliance modeling
Cashflow waterfall structure
Stress testing scenarios
Vintage cohort performance tracking
Interactive investor dashboards
Crisis simulation (Risk Arena)

Stress Testing Scenarios
Base Scenario
Mild Stress (+25% loss)
Severe Stress (+50% loss)
Tranche Structure
Senior Tranche → 80%
Mezzanine Tranche → 15%
Equity Tranche → 5%
Tools & Technologies
Power BI
DAX (Data Analysis Expressions)
Power Query
Excel
Financial Risk Modeling

Key Insights
Higher DPD buckets show increased credit risk
Expected Loss rises significantly under stress scenarios
Senior tranche remains protected in most conditions
Vintage analysis helps identify risky loan cohorts

Conclusion

This project demonstrates a complete end-to-end securitisation risk analytics system, combining financial risk modeling, IFRS 9 compliance, and interactive business intelligence dashboards.

It provides actionable insights for risk managers, analysts, and investors.

Dashboard Images
 Executive Dashboard

![Executive Dashboard](images/Executive%20Dashboard.png)
DPD Analysis

![DPD Analysis](images/DPD%20Analysis.png)
IFRS 9 Dashboard

![IFRS 9 Dashboard](images/IFRS%209%20Dashboard.png)
Investor Reporting

![Investor Reporting](images/Investor%20Reporting.png)
Vintage Analysis

![Vintage Analysis](images/Vintage%20Analysis.png)
 Waterfall & Tranche Analysis

![WaterFall Tranche](images/WaterFall%20Tranche.png)
Stress Testing Framework

![Stress Testing](images/Stress%20Testing%20Framework.png)



👨‍💻 Author

Koduri Thanay Chowdary
Data Analyst | Power BI | Risk Analytics
