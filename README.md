# Luxury-Housing-Sales-Analysis-Bengaluru
Problem Statement:
Build a complete real estate analytics solution using Python for advanced data cleaning, load the refined dataset into a SQL database, and use Power BI to directly connect to SQL and build a dashboard. The goal is to replicate a real-world enterprise-level data pipeline and analysis environment using a complex housing dataset with 1,00,000+ records.
# Skills take away From This Project
 1) Data Cleaning using Python (Pandas, NumPy)
 2) Data Preprocessing and Transformation
 3) SQL Data Warehousing and Querying
 4) Building Interactive Dashboards using Power BI
 5) Data Visualization and Storytelling
 6) Exploratory Data Analysis (EDA)
 7) Business Insight Generation
 8) Real Estate Market Analytics
# Business Usecase:
 1) Market Intelligence: Identify high-performing localities, builder-wise trends, and configuration demand shifts.
 2) Sales Optimization: Use booking and inquiry data to uncover drop-off patterns.
 3) Buyer Persona Building: Use Buyer Type and Comment sentiment to group and understand buyer personas.
 4) Competitive Pricing: Analyze pricing strategies across builders and market segments.
 5) Amenity Score & Conversion: Determine the correlation between amenities and booking rates.
 6) Quarterly Trend Tracking: Track real estate patterns across fiscal quarters to aid investment decisions.
# Python Data Cleaning and Feature Engineering
 1) cleaned 100K + raw records by removing Duplicte rows and missing null values imputation by analysing weather the column is Normaly Distributed or skewed and then filing      the missing values with (Mean,Median,Mode).
 2) Then while null value imputation in Ticket_Price_Cr Feature  not only applying median to those missing values , we are analysing the Configuration [5BHK,4BHK,3BHK] ,BY       what are the ticket_price for those BHK in particular Datapoint.
 3) Source Code for above null value Imputation:
     median_val = df.loc[df['Configuration'].isin(['5Bhk+ ', '5BHK+', '5bhk+']),'Ticket_Price_Cr'].median()
     median_val
     df.loc[df['Ticket_Price_Cr'].isnull() & df['Configuration'].isin(['5Bhk+', '5BHK+', '5bhk+']),'Ticket_Price_Cr'] = median_val
     median_val_1 = df.loc[df['Configuration'].isin(['4BHK', '4Bhk', '4bhk']),'Ticket_Price_Cr'].median()
     median_val_1
     df.loc[df['Ticket_Price_Cr'].isnull() & df['Configuration'].isin(['4BHK', '4Bhk', '4bhk']),'Ticket_Price_Cr'] = median_val_1
     median_val_2 = df.loc[df['Configuration'].isin(['3BHK ', '3bhk', '3Bhk']),'Ticket_Price_Cr'].median()
     median_val_2
     df.loc[df['Ticket_Price_Cr'].isnull() & df['Configuration'].isin(['3BHK ', '3bhk', '3Bhk']),'Ticket_Price_Cr'] = median_val_2
#  SQL – Data Warehousing & Analysis
    Created a MySQL database luxury_housing_bangalore_db Inserted cleaned dataset into table luxury_properties using SQLAlchemy Validated data insertion with COUNT, GROUP        BY, and AVG queries Ensured normalized structure for efficient querying
    Ran validation & analytical queries, e.g.:
    SELECT COUNT(*) FROM housing_sales; SELECT Builder, AVG(Ticket_Price_Cr) FROM housing_sales GROUP BY Builder; SELECT Micro_Market, SUM(Bookings) FROM housing_sales GROUP     BY Micro_Market;
    Supported KPIs & Power BI integration directly from SQL.
# Power BI — Visualize via Direct SQL Connection
    Connected dashboard to SQL database.
    Built interactive visuals with filters (Builder, Market, Quarter, Price Range).
    Created custom DAX measures:
    Booking Conversion Rate (%)
    Average Ticket Price per Builder
    Market Share by Micro-Market
# Key Visualizations:
    Line Chart with Quarter on X-axis and Booking_Count on Y-axis, segmented by Micro_Market
    Bar Chart or Table showing Builder, Sum(Ticket_Price_Cr), Avg(Ticket_Price_Cr)
    Scatter plot: Amenity_Score vs Booking_Conversion_Rate, with bubble size by Project Count
    Stacked Column Chart: Micro_Market with % Booking_Status as stacked sections
    Pie Chart or Donut Chart of Configuration vs Booking Count
    100% Stacked Column Chart: Sales_Channel vs Booking_Status distribution etc....
 # Tech Stack:
    Python → Pandas, NumPy, SQLAlchemy
    SQL → MySQL / sqlalchemy
    Visualization → Power BI (Visualizations)
    Domain → Real Estate Analytics
  # Results
   ✔ 100,000+ rows cleaned, standardized, and stored in SQL. ✔ Power BI dashboard with interactive, filter-based insights. ✔ Builder, buyer, and market-level intelligence        for strategic decisions. ✔ Replicates a real-world BI pipeline for real estate analytics.

 # Skills & Learning Outcomes
    Advanced Data Cleaning & Preprocessing
    SQL Schema Design & Analytical Queries
    Power BI Dashboards & DAX Calculations
    Exploratory Data Analysis (EDA)
    Business Insights & Storytelling
    Luxury Real Estate Market Analytics
 # Acknowledgments
   This project combines business intelligence, data engineering, and analytics to transform 100,000+ housing records into actionable insights for the luxury housing market     in Bengaluru.

