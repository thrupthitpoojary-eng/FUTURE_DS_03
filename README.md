# Marketing Funnel Performance Analysis

## 1. Project Overview

This project focuses on analyzing marketing funnel data to identify conversion patterns, understand lead performance, and measure the progress of marketing-qualified leads into closed deals. The analysis was performed using Microsoft Power BI to explore marketing sources, conversion rates, and different business categories.

An interactive dashboard was developed to present key performance indicators and visual insights into marketing funnel performance.

## 2. Project Objectives

The main objectives of this project are:

- Analyze marketing-qualified leads and closed deals.
- Calculate the lead-to-customer conversion rate.
- Identify the number of converted and unconverted leads.
- Compare lead generation and closed deals across different marketing sources.
- Analyze closed deals based on business type, business segment, and lead type.
- Identify monthly trends in closed deals.
- Create an interactive dashboard to present the analysis.

## 3. Dataset Description

The dataset used for this project is the **Olist Marketing Funnel Dataset**, obtained from Kaggle.

The dataset consists of two CSV files:

### 3.1 Marketing Qualified Leads Dataset

Contains information about potential customers who showed interest in the business.

| Column Name | Description |
|---|---|
| mql_id | Unique ID of each marketing-qualified lead |
| first_contact_date | Date of the first contact with the lead |
| landing_page_id | ID of the landing page |
| origin | Source from which the lead originated |

### 3.2 Closed Deals Dataset

Contains information about marketing-qualified leads that successfully converted into closed deals.

| Column Name | Description |
|---|---|
| mql_id | Unique ID of the marketing-qualified lead |
| seller_id | Unique ID of the seller |
| sdr_id | ID of the Sales Development Representative |
| sr_id | ID of the Sales Representative |
| won_date | Date when the deal was successfully closed |
| business_segment | Business segment of the deal |
| lead_type | Type of lead |
| business_type | Type of business |

Both datasets were connected using the common column `mql_id`.

## 4. Tools and Technologies Used

- **Microsoft Power BI:** Used for data analysis and dashboard creation.
- **Power Query:** Used for importing and preparing the datasets.
- **DAX:** Used to create calculated measures and key performance indicators.
- **Kaggle:** Used to download the dataset.

## 5. Data Import and Preparation

1. Downloaded the Olist Marketing Funnel Dataset from Kaggle.
2. Extracted the downloaded ZIP file.
3. Imported both CSV files into Power BI Desktop.
4. Checked the columns and data types in the datasets.
5. Established a relationship between the two tables using the common `mql_id` column.
6. Created DAX measures to calculate total leads, closed deals, conversion rate, and unconverted leads.
7. Used the prepared data to create different visualizations.

## 6. DAX Measures

The following DAX measures were created to perform the analysis:

### 6.1 Total Leads

```DAX
Total Leads =
DISTINCTCOUNT(
    olist_marketing_qualified_leads_dataset[mql_id]
)
```

### 6.2 Total Closed Deals

```DAX
Total Closed Deals =
DISTINCTCOUNT(
    olist_closed_deals_dataset[mql_id]
)
```

### 6.3 Lead Conversion Rate

```DAX
Lead Conversion Rate =
DIVIDE(
    [Total Closed Deals],
    [Total Leads],
    0
)
```

### 6.4 Unconverted Leads

```DAX
Unconverted Leads =
[Total Leads] - [Total Closed Deals]
```

## 7. Key Performance Indicators (KPIs)

The following KPIs were created to measure marketing funnel performance:

1. **Total Leads:** Displays the total number of marketing-qualified leads.
2. **Total Closed Deals:** Displays the total number of leads that successfully converted into closed deals.
3. **Lead Conversion Rate:** Displays the percentage of leads converted into closed deals.
4. **Unconverted Leads:** Displays the number of leads that did not convert into closed deals.

## 8. Dashboard Visualisations

The Power BI dashboard includes:

1. **KPI Cards:** Total leads, total closed deals, lead conversion rate, and unconverted leads.
2. **Total Leads by Marketing Source:** Compares the number of leads generated from different marketing sources.
3. **Closed Deals by Marketing Source:** Shows the number of successfully closed deals from different marketing sources.
4. **Conversion Rate by Marketing Source:** Compares conversion rates across different marketing sources.
5. **Closed Deals by Business Type:** Analyzes closed deals based on business type.
6. **Closed Deals by Business Segment:** Compares closed deals across different business segments.
7. **Closed Deals by Lead Type:** Shows the distribution of closed deals based on lead type.
8. **Monthly Closed Deals Trend:** Displays the monthly trend of successfully closed deals.
9. **Interactive Slicers:** Marketing source and lead creation date filters to explore the dashboard.

## 9. Conclusion

This project helped in understanding marketing funnel analysis and the importance of tracking lead conversion performance. By analyzing marketing-qualified leads and closed deals, different marketing sources and business categories were explored to understand their contribution to successful conversions.

The interactive Power BI dashboard presents the analysis through KPI cards, charts, and slicers, making it easier to understand and explore marketing funnel performance.

Through this task, I gained practical experience in Power BI, Power Query, DAX, data analysis, and dashboard development.
