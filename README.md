# gtc-ml-project1-hotel-bookings
Hotel Booking Data Cleaning & Preparation
Project Overview

This project focuses on cleaning, exploring, and preparing the Hotel Booking Dataset for further analysis and machine learning tasks.
The dataset contains booking information for city hotels and resort hotels, including details such as guest demographics, booking channels, cancellations, and stay durations.

The goal is to:

Identify and fix data quality issues (missing values, outliers, incorrect data types, duplicates).

Create new features for better insights.

Prepare the dataset for machine learning models by encoding categorical variables and splitting into training and testing sets.

Steps Performed
1. Exploratory Data Analysis (EDA)

Inspected dataset shape and column types.

Checked for missing values and duplicates.

Visualized missing values with heatmaps/matrices.

Detected outliers in key numeric columns (adr, lead_time) using boxplots and the IQR method.

2. Handling Missing Values

Agent & Company → filled with "None" (missing means no agent/company used).

Country → filled with "Unknown" (couldn’t identify guest country).

Children → filled with median (to keep distribution stable).

3. Removing Duplicates

Dropped exact duplicate rows to avoid data bias.

4. Handling Outliers

ADR (Average Daily Rate): capped extreme values above 1000.

Lead Time: capped values above 365 days (1 year).

5. Fixing Data Types

Converted date-related columns to datetime.

Converted categorical IDs (agent, company) to object type.

6. Feature Engineering

total_guests = adults + children + babies.

total_nights = stays in weekend + stays in week nights.

is_family = Yes/No flag if children or babies included.

7. Encoding Categorical Variables

Low-cardinality features (meal, market segment, deposit type, etc.) → One-Hot Encoding.

High-cardinality feature (country) → grouped infrequent countries into "Other" + One-Hot Encoding.

8. Preventing Data Leakage

Dropped reservation_status and reservation_status_date (not available at booking time).

9. Train-Test Split

Split dataset into:

80% training set

20% testing set

Used random_state=42 for reproducibility.

Tools & Libraries

Python

Pandas & NumPy → data manipulation

Matplotlib & Seaborn → data visualization

Missingno → missing value visualization

Scikit-learn → preprocessing & train-test split

Key Findings

Dataset contained missing values mainly in agent, company, country, and children.

Outliers detected in ADR (negative values and very high values).

Duplicates existed and were removed.

Created new features (total_guests, total_nights, is_family) to enrich analysis.
