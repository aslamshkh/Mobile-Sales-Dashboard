# 📱 Mobile Sales Dashboard

## 📑 The Table Of Contents
- [Purpose](#purpose)
- [Performance Indicators](#performance-indicators)
- [Data Overview](#data-overview)
- [Initial Data Observations](#initial-data-observations)
- [Data Loading](#data-loading)
- [Data Cleaning And Transformation](#data-cleaning-and-transformation)
- [Data Exploration And Key Insights](#data-exploration-and-key-insights)
- [Dashboard Creation](#dashboard-creation)

---

## 🎯 Purpose

This project aims to enhance strategic decision-making in the mobile retail sector through a data-driven sales analytics dashboard. Built entirely in Microsoft Power BI, the solution leverages Power Query, DAX, and interactive visuals to analyze sales performance, customer behavior, and brand trends across India.

The dashboard is designed for retail managers, marketing teams, and business analysts, transforming raw transactional data into a dynamic, filterable interface. It supports smarter inventory planning, targeted promotions, and a deeper understanding of consumer preferences. The solution is scalable, visually intuitive, and accessible via the Power BI Service—making it ideal for both internal reporting and public portfolio sharing.

---

## 📊 Performance Indicators

- **Total Sales**: Overall revenue generated from mobile phone transactions across all cities and brands.
- **Total Quantity Sold**: Total number of mobile units sold during the selected time period.
- **Total Transactions**: Number of completed sales transactions recorded in the dataset.
- **Average Price per Unit**: Average selling price per mobile unit, calculated across all transactions.
- **Customer Ratings**: Distribution of satisfaction scores (1 to 5 stars) provided by customers post-purchase.
- **Sales by Brand and Model**: Revenue and quantity breakdown by individual mobile models and their respective brands.
- **Payment Method Share**: Percentage distribution of transactions across payment modes (Cash, UPI, Credit Card, Debit Card).
- **Sales by City**: Geographic distribution of sales volume and revenue across Indian cities.
- **Sales by Day of Week**: Analysis of sales trends across weekdays to identify peak business days.

---

## 📁 Data Overview

This project is based on a publicly available dataset from a Github repositry. The dataset contains 3835 records and 14 columns, each representing key attributes of mobile phone sales such as transaction details, customer ratings, brand, and product specifications.

## 🧾 Dataset Summary

- **Format**: Excel 
- **Rows**: 3835 (including header)  
- **Columns**: 14 
- **Time Period Covered**: 2021 to 2024 (based on dates)

---

## 🔍 Initial Data Observations

The dataset appeared mostly clean and structured, but a few adjustments were necessary to prepare it for analysis and dashboard creation:

- Dates were split across three columns: Year, Month, and Date. These needed to be merged into a single column to support time-based filtering and trend analysis.
- The Day Name column contained inconsistent values (e.g., "Fr" and "Friday") that required standardization for accurate weekday-level insights.
- No direct column for Total Sale or Profit was available. However, Unit Sold and Price per Unit were present, allowing us to derive Total Sales using a calculated column.
- No blank or empty cells were found in the dataset, which minimized the need for null handling.

---

## 📥 Data Loading

The dataset was first imported into Excel and then loaded into Power BI for transformation and modeling:

- Imported the raw data into Excel using:  
  **Data tab → Get Data → From File → From Text/CSV**

- Verified the column structure and data types in the Navigator window to ensure proper alignment and formatting.

- Loaded the dataset into **Power BI Power Query Editor** for further cleaning and transformation before integrating it into the data model.

---

## 🧹 Data Cleaning and Transformation

<details>
<summary>1. Error and Column Quality Check</summary>

 Used **View > Column Quality** to check for errors, empty cells, and invalid entries.  
 ✅ No issues were found — all columns were clean and complete.

</details>

<details>
<summary>2. Inspection Before Loading</summary>

 Verified column structure and data types in the **Navigator Window** before loading into Power Query Editor.  
 Ensured the correct Excel sheet was selected for transformation and modeling.

</details>

<details>
<summary>3. Date Column Merging</summary>

 Merged the Year, Month, and Date columns into a single Date column using:  
 **Transform > Merge Columns**  
 - Added a separator  
 - Renamed the column  
 - Changed data type to **Date**

</details>

<details>
<summary>4. Day Name Standardization</summary>

 Used **Transform > Replace Values** to clean inconsistent weekday names:  
 - "Fr" → "Friday"  
 - "Mon" → "Monday"  
 - "Sat" → "Saturday"  
 ...and so on for the full week.

</details>

<details>
<summary>5. Customer Calendar Creation</summary>

 Created a custom date table to handle missing dates and enable dynamic slicers.

 - Used: **Home > New Query > Blank Query**  
 - Applied formula:  
   `= List.Dates(#date(2021,01,01), 1461, #duration(1,0,0,0))`  
 - Renamed the column and query  
 - Changed data type to **Date**  
 - Extracted **Day Name** column for weekday analysis

</details>

<details>
<summary>6. Duplicate Check</summary>

 Used **Home > Keep Rows > Keep Duplicates** to check for duplicate records.  
 ✅ No duplicate rows were found.

</details>

<details>
<summary>7. Final Load</summary>

 Renamed the cleaned query and applied changes using:  
 **Home > Close & Apply**  
 Data was successfully loaded into Power BI for modeling and visualization.

</details>

---

## 💡 Data Exploration and Key Insights

After completing the data cleaning and transformation steps, I explored the dataset using Power BI visuals and DAX measures to uncover trends in sales performance, customer behavior, a
nd brand dynamics. The following insights were identified:

- Sales remained consistent across the three-year period, with slight dips observed in February and September.
- Thursday and Saturday emerged as the highest-performing days in terms of total sales volume.
- Vivo and Apple were the top-performing brands, both in terms of revenue and customer satisfaction.
- The best-selling models were Vivo S1 (₹6.6M), Vivo V20 (₹6.4M), and iPhone 11 (₹5.7M).
- Cash and UPI were the most preferred payment methods, together accounting for over 50% of all transactions.
- Customer ratings were mostly positive, with the majority of feedback falling in the 4–5 star range.
- Sales were concentrated in metro cities, indicating stronger demand in urban regions.
- No extreme seasonal spikes were observed, suggesting steady demand throughout the year.

---

## 🛠️ Dashboard Creation

The dashboard was built in Power BI with a clean, interactive layout designed for clarity, usability, and insight discovery. Key formatting and design steps included:

- A consistent color scheme and layout to ensure visual balance and readability.
- Slicers for Year, Month, Brand, Model, and Payment Method to enable dynamic filtering.
- Custom tooltips and dynamic titles to enhance user experience and context awareness.
- All visuals were arranged to guide the user from high-level KPIs to detailed breakdowns.

### Visual Overview

- **KPI Cards**: Displayed Total Sales, Quantity Sold, Total Transactions, and Average Price per Unit for quick performance tracking.

- **Map Visual**: Showed geographic distribution of mobile sales across Indian cities.

- **Line Chart**: Illustrated monthly quantity trends to identify seasonal patterns and dips.

- **Bar Charts**:
  - Customer Ratings distribution (1 to 5 stars)
  - Sales by Day of the Week
  - Brand-wise performance in terms of revenue and transaction count

- **Pie Chart**: Represented the share of payment methods used (Cash, UPI, Credit Card, Debit Card).

- **Table Visual**: Detailed sales and transaction data by mobile model and brand for granular analysis.

The dashboard was published to Power BI Service for web-based access and portfolio presentation.

![image](https://github.com/aslamshkh/Mobile_Sales_Dashboard/blob/main/Mobile%20Sale%20Dashboard.png)



