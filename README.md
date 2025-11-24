# EnergyIot
Smart Energy IoT – End-to-End Data Engineering & Analytics Pipeline
An end-to-end Smart Energy IoT pipeline covering the full data lifecycle — from ingestion and ETL to Business Database (3NF), Data Warehouse (Star Schema + SCD2), and analytics-ready datasets for forecasting and sensor intelligence.

This project demonstrates real-world data engineering architecture using an enriched smart-grid IoT dataset and follows best practices in modularity, documentation, and reproducibility.

📌 Project Overview
This repository implements a complete modern data pipeline:

1. Raw Data Ingestion
Source: Smart Grid Smart City Dataset (Kaggle)
Files stored in: data/raw/
Includes hourly energy consumption, weather conditions, sensor metadata, and city-level environmental metrics.
2. ETL & Data Cleaning
Located in: data-engineering/

Handling missing values
Type casting & normalization
Temporal feature extraction
Geospatial consistency checks
Output stored in: data/cleaned/
3. Business Database (3NF Model)
Located in: data/db/

A properly normalized 3rd Normal Form schema
Entities include:
Households
Sensors
EnergyUsage
Weather
TimeDimension
Ensures consistency and reduces redundancy for applications & analytics.
4. Data Warehouse (Star Schema + SCD Type 2)
Fact tables:
fact_energy_usage
Dimension tables:
dim_household (SCD Type 2)
dim_sensor
dim_time
dim_weather
Used for BI dashboards and ML pipelines.
5. Diagrams & Documentation
All diagrams stored under data-engineering/diagrams/:

ER diagrams (Draw.io + PNG exports)
3NF schema
Star Schema DWH Layout
SCD Type 2 tracking flow
📊 Dataset Description (Smart Grid Dataset)
File: smart_grid_dataset_city_hourly_enriched.csv
Location: data/raw/

This dataset contains hourly city-level energy & environmental measurements, including:

Column	Description
hour	Timestamp of measurement
energy_consumption_kwh	Hourly electricity usage
temperature	Outdoor temperature
humidity	Ambient humidity level
solar_radiation	Solar irradiance in W/m²
wind_speed	Wind in m/s
is_holiday	Binary flag
city_zone	City sector identifier
sensor_id	Device generating the reading
… many more enriched environmental + IoT metrics	
This dataset forms the basis for building both the business database and analytical warehouse.

📁 Repository Structure
project/
│
├── data/
│   ├── raw/                # Original Kaggle dataset (CSV)
│   ├── cleaned/            # ETL output
│   └── db/                 # Final SQLite DB (3NF + DWH)
│
├── data-engineering/
│   ├── diagrams/           # ER, 3NF, DWH diagrams
│   ├── sql/                # SQL scripts for DB + DWH
│   └── docs/               # Additional documentation
│
├── README.md               # Main project documentation
└── ...
🏗️ Technologies Used
SQL (SQLite)
Python (ETL, preprocessing)
Draw.io (architecture & schema diagrams)
Pandas / Numpy
Data Warehousing concepts:
3NF normalization
Star Schema
Slowly Changing Dimensions (SCD Type 2)
📦 Final Database
File: smart_city_iot.db
Location: data/db/

Contains:

Cleaned and validated energy, weather & sensor data
Normalized business schema (3NF)
Fully designed Data Warehouse (DWH) with SCD2
Ready for BI tools (Tableau, PowerBI) & ML modeling
📜 Author & Copyright
Author: Dr. Mahrokh Javadi
Year: 2025
License: All rights reserved unless stated otherwise.
You may view, fork, and study the code.
Redistribution or commercial use requires permission from the author.

🤝 Contributions
This is a personal academic/portfolio project.
Feel free to submit issues or contribute improvements.

⭐ Support
If you found this useful, give the project a star to support further development!
