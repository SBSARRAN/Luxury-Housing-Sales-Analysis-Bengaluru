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
 4) 
     median_val = df.loc[df['Configuration'].isin(['5Bhk+ ', '5BHK+', '5bhk+']),'Ticket_Price_Cr'].median()
     median_val
     df.loc[df['Ticket_Price_Cr'].isnull() & df['Configuration'].isin(['5Bhk+', '5BHK+', '5bhk+']),'Ticket_Price_Cr'] = median_val
     median_val_1 = df.loc[df['Configuration'].isin(['4BHK', '4Bhk', '4bhk']),'Ticket_Price_Cr'].median()
     median_val_1
     df.loc[df['Ticket_Price_Cr'].isnull() & df['Configuration'].isin(['4BHK', '4Bhk', '4bhk']),'Ticket_Price_Cr'] = median_val_1
     median_val_2 = df.loc[df['Configuration'].isin(['3BHK ', '3bhk', '3Bhk']),'Ticket_Price_Cr'].median()
     median_val_2
     df.loc[df['Ticket_Price_Cr'].isnull() & df['Configuration'].isin(['3BHK ', '3bhk', '3Bhk']),'Ticket_Price_Cr'] = median_val_2

