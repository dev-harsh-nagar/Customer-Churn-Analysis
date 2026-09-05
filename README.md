# Customer-Churn-Analysis
PulseNet is a fictional subscription/customer-service business. Leadership wants to understand who is leaving, which customer segments show higher churn, where churn is concentrated, and what customer or revenue exposure may deserve at

PulseNet Customer Churn Analytics

An end-to-end Data Analyst portfolio project using Python, SQL,
and Tableau to investigate customer churn, identify important
associated patterns, and quantify customer/revenue exposure.

Note: PulseNet is a fictional dataset created for
portfolio/practice purposes. The analysis is descriptive and does not
establish causation.

Project Overview

PulseNet's leadership team wants to understand:

How large is the customer churn problem?

Which plans, contract types, regions, acquisition channels, and
devices show higher churn?

What payment, support, satisfaction, and usage patterns are
associated with churn?

Where is churned-customer revenue exposure concentrated?

What areas should be investigated for retention opportunities?

Workflow: Data Understanding → Cleaning & QA → Python Analysis → SQL
Analysis → Tableau → QA → Business Recommendations

Key Results

Metric                                                           Result

Total customers                                                  12,000

Active customers                                                 10,394

Churned customers                                                 1,606

Overall churn rate                                               13.38%

Cleaned payment records                                         117,501

Successful payments                                             108,402

Failed payments                                                   9,099

Churn period                                           March--June 2026

Peak monthly churn                           May 2026 --- 477 customers

Selected observations

Monthly contracts have the highest observed churn rate at
17.45%, versus 11.14% for quarterly and 6.54% for annual
contracts.

Basic plan has the highest observed plan churn at 15.65%.

Partner acquisition has the highest observed acquisition-channel
churn at 14.69%.

Web has the highest observed primary-device churn at 14.28%.

May 2026 recorded the highest monthly churn count with 477
churned customers.

Historical successful payment value associated with churned
customers totals ₹23.72M.

These are descriptive associations in the fictional dataset and should
not be interpreted as causal findings.

Dataset

Table                   Primary Key             Purpose

customers             Customer_ID           Customer profile,
acquisition, status and
churn date

payments              Payment_ID            Payment transactions
and payment status

subscriptions         Subscription_ID       Plan, fee, contract and
support tier

support_tickets       Ticket_ID             Support contacts,
resolution and
satisfaction

Customer_ID is unique in customers and is reused as the logical
foreign key in the other four tables.

Data Cleaning & QA

Important decisions included:

Kept Customer_ID as text/VARCHAR because values such as
CUST00001 are identifiers, not measures.

Removed 20 exact duplicate payment records, reducing payments
from 117,521 to 117,501 rows.

Converted blank active-customer Churn_Date values to true NULL
values.

Retained 35 missing Satisfaction_Score values as legitimate
missing data.

Added and validated primary keys for all five tables.

Converted and validated date fields and checked important
numeric/category fields.

Join-safety

Payments, support tickets and monthly usage contain multiple records per
customer. Raw joins across several one-to-many tables can multiply rows
and inflate totals.

For customer-level metrics, child tables should be aggregated by
Customer_ID before combining multiple one-to-many sources.

Python Analysis

Python/pandas was used for:

Data profiling

Null and duplicate checks

Datatype conversion

Data cleaning

Churn calculations

Customer segmentation

Payment analysis

Customer-level payment value

Support and usage analysis

Validation before SQL/Tableau

SQL Analysis

MySQL was used to independently answer 20 business questions covering:

Overall churn rate

Churn by region, state and city

Churn by acquisition channel and primary device

Average customer lifetime before churn

Current active customers

Monthly churn trend

Churned customer profile

Successful revenue

Revenue by payment method

Monthly revenue

Failed amount by payment method

Payment failure rate by method

Average payment amount: Active vs Churned

Customer value vs churn

Churn rate by subscription plan

Average support resolution: Active vs Churned

Average satisfaction: Active vs Churned

Churn by satisfaction group

Average usage hours: Active vs Churned

Average usage issue count: Active vs Churned

Tableau Dashboards

1. Executive Churn Overview

Question: How large is the churn problem?

Includes:

Total Customers

Churn Rate

Active vs Churned Customers

Monthly Churn Trend

Churn Rate by Contract Type

Churn Rate by Region

Churn Rate by Plan

2. Churn Drivers

Question: Which customer, payment, support and usage dimensions are
associated with higher churn?

Includes:

Churn Rate by Tenure

Churn Rate by Acquisition Channel

Churn Rate by Primary Device

Payment Failure Rate

Support resolution comparison

Satisfaction comparison

Satisfaction-group churn

Usage comparisons

Plan × Contract Type churn heatmap

3. Customer & Revenue Impact

Question: Where is business exposure concentrated?

Includes:

Historical successful payment value associated with churned
customers

Revenue exposure by plan

Acquisition-channel performance

Top cities by churned customers

Business Recommendations

Investigate monthly-contract retention because monthly contracts
have the highest observed churn rate.

Review the Basic plan experience because it has the highest
observed plan churn.

Audit Partner acquisition because it has the highest observed
acquisition-channel churn.

Investigate the May churn spike because May has the highest
monthly churn count.

Prioritize high-value churn exposure using customer value
alongside churn counts and rates.

Use churn rate and churn count together: rate supports fair
comparison, while count/value supports absolute prioritization.

Repository Structure

PulseNet-Customer-Churn-Analytics/
│
├── README.md
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_cleaning_and_qa.ipynb
│   └── 03_eda_and_insights.ipynb
│
├── sql/
│   ├── 01_schema.sql
│   ├── 02_basic_analysis.sql
│   ├── 03_churn_analysis.sql
│   └── 04_advanced_analysis.sql
│
├── tableau/
│   └── PulseNet_Churn_Analytics.twbx
│
├── screenshots/
│   ├── dashboard_1_executive_overview.png
│   ├── dashboard_2_churn_drivers.png
│   └── dashboard_3_customer_revenue_impact.png
│
└── documentation/
    └── PulseNet_Customer_Churn_Analytics_Documentation.pdf

Tools & Skills

Python: pandas, data cleaning, exploratory analysis, datetime
handling, grouping, aggregation, validation

SQL / MySQL: SELECT, WHERE, GROUP BY, ORDER BY, CASE WHEN, COUNT,
SUM, AVG, JOINs, subqueries/CTEs, data-quality validation

Tableau: calculated fields, KPI dashboards, filters, trend analysis,
churn analysis, heatmaps, dashboard storytelling

Analytics: customer churn, segmentation, customer value, payment
behavior, support analysis, usage/engagement analysis, data QA

Limitations

PulseNet is a fictional dataset.

The analysis is observational and descriptive.

Higher churn in a segment does not prove that the segment
characteristic caused churn.

Historical successful payment value associated with churned
customers should not be described as guaranteed future revenue loss
or recurring revenue without a suitable revenue model.

Portfolio Note

This project demonstrates a complete practical Data Analyst workflow:
starting with business questions, validating and cleaning data,
reproducing analysis in SQL, building management-oriented Tableau
dashboards, and translating results into business recommendations.
