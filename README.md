# New York Taxi Trip Data Analysis

## New York Taxi Trip Dataset

The New York City Yellow Taxi Trip Dataset contains detailed records of taxi rides collected and published by the NYC Taxi and Limousine Commission (TLC).  
Each record includes pickup and drop-off timestamps and locations, trip distance, passenger count, fare components, payment type, tips, and total trip cost.

The dataset used in this project covers **five years (2020–2024)** and originally contains over **160 million trips**, making it suitable for large-scale data processing and analysis. Due to its size and real-world nature, the dataset presents typical Big Data challenges such as missing values, inconsistent schemas, duplicates, and extreme outliers.

## Goal of the Analysis

The goal of this project is to **extract actionable insights from large-scale taxi trip data** that can support decision-making aimed at improving service efficiency and profitability.  
The analysis focuses on identifying temporal, spatial, and pricing patterns in taxi trips, understanding customer payment behavior, and comparing trends with competing ride-hailing services.

## Technologies and Data Preprocessing

This project uses **PySpark** as the primary Big Data processing framework to efficiently handle hundreds of millions of records.

### Data preprocessing steps:
- Reading monthly data files into **Spark DataFrames** and unifying schemas  
- Handling missing values using:
  - Median imputation for skewed numerical features (e.g., passenger count)
  - Rule-based imputation for tariff codes based on drop-off location  
- Removing invalid and low-frequency payment types  
- Dropping redundant columns already included in the total fare  
- Removing duplicate records  
- Filtering extreme outliers for:
  - Trip distance
  - Fare amount
  - Total amount
  - Tip amount  
- Feature engineering:
  - Trip duration
  - Time-of-day categories

After preprocessing, the dataset was reduced to approximately **139 million clean records**.

## Data Analysis

The analysis consists of several components:

- **Correlation analysis** to identify relationships between numerical features such as fare, trip distance, tips, and total amount  
- **Temporal analysis** of daily and monthly trip volumes to detect long-term trends  
- **Peak hour analysis** using heatmaps to identify periods of highest taxi demand  
- **Pricing analysis** comparing demand intensity with average trip cost during peak hours  
- **Payment type analysis**, highlighting the dominance of credit card usage and its impact on tipping behavior  
- **Spatial analysis** of pickup and drop-off locations to identify high-traffic zones such as city centers and airports  
- **Comparative trend analysis** of Yellow Taxi, Uber, and Lyft trip volumes, revealing similar growth patterns influenced by external factors (e.g., COVID-19)

Based on the results, the project proposes data-driven recommendations such as dynamic pricing during peak hours, enhanced tip promotion strategies, and optimization of taxi distribution across city regions.

## Technologies Used

- Python  
- PySpark  
- Pandas  
- Matplotlib / Seaborn  
- Big Data processing with Apache Spark
