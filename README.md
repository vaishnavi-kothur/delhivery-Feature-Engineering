# Delhivery Logistics Analytics & Feature Engineering

## Project Overview

Delhivery is India's largest integrated logistics and supply chain company, handling millions of shipments across the country.

This project focuses on cleaning, transforming, and engineering features from raw logistics data to improve delivery analytics and support predictive modeling. The objective is to prepare high-quality data for forecasting delivery performance and optimizing logistics operations.

---

## Business Problem

Delhivery wants to:

* Process and clean data generated from logistics operations
* Create meaningful features from raw shipment data
* Improve delivery time prediction accuracy
* Identify operational inefficiencies
* Enable the data science team to build forecasting and optimization models

The goal is to convert raw transportation data into actionable business insights.

---

## Dataset Information

The dataset contains shipment-level and route-level delivery information.

### Features

| Feature                        | Description                         |
| ------------------------------ | ----------------------------------- |
| trip_uuid                      | Unique trip identifier              |
| route_type                     | Transportation mode (FTL / Carting) |
| source_center                  | Source warehouse                    |
| destination_center             | Destination warehouse               |
| trip_creation_time             | Trip creation timestamp             |
| od_start_time                  | Origin-Destination start time       |
| od_end_time                    | Origin-Destination end time         |
| actual_distance_to_destination | Actual delivery distance            |
| actual_time                    | Actual delivery time                |
| osrm_time                      | Predicted route time                |
| osrm_distance                  | Predicted route distance            |
| segment_actual_time            | Segment-level delivery time         |
| segment_osrm_time              | Segment-level predicted time        |
| segment_osrm_distance          | Segment-level predicted distance    |

---

## Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Scikit-Learn
* Jupyter Notebook

---

## Data Preprocessing

Performed:

* Missing value treatment
* Duplicate record removal
* Data type validation
* Outlier detection using IQR
* Data aggregation using GroupBy
* Feature extraction from datetime columns

---

## Feature Engineering

### Route Aggregation

Merged multiple shipment segments into trip-level records using:

* trip_uuid
* source_center
* destination_center

Aggregated:

* Distance
* Time
* Segment metrics

to create a complete trip profile.

### Time-Based Features

Extracted:

* Year
* Month
* Day
* Weekday
* Hour

from:

* trip_creation_time
* od_start_time

### Location-Based Features

Extracted:

* City
* State
* Area Code

from:

* source_name
* destination_name

### Delivery Duration Feature

Created:

Delivery Duration = od_end_time - od_start_time

to measure actual transit performance.

---

## Exploratory Data Analysis

### Univariate Analysis

* Delivery Distance Distribution
* Delivery Time Distribution
* Route Type Distribution
* Corridor Analysis

### Bivariate Analysis

* Actual Time vs OSRM Time
* Actual Distance vs OSRM Distance
* Route Type vs Delivery Time
* Source-Destination Analysis

### Correlation Analysis

* Heatmap of numerical features
* Relationship between delivery time and distance variables

---

## Statistical Validation

Performed visual and statistical comparison between:

### Time Analysis

* Actual Time vs OSRM Time
* Actual Time vs Segment Actual Time
* OSRM Time vs Segment OSRM Time

### Distance Analysis

* OSRM Distance vs Segment OSRM Distance

Objective:

Evaluate prediction accuracy and identify deviations between estimated and actual logistics performance.

---

## Outlier Treatment

Applied:

### IQR Method

Handled outliers in:

* Actual Time
* Delivery Distance
* OSRM Time
* Segment Metrics

Benefits:

* Reduced skewness
* Improved model readiness
* Enhanced data quality

---

## Data Transformation

### Categorical Encoding

Applied One-Hot Encoding on:

* Route Type
* State
* City Categories

### Feature Scaling

Applied:

* StandardScaler
* MinMaxScaler

to normalize numerical features for machine learning applications.

---

## Key Insights

### Route Performance

* FTL routes generally handle longer distances with more consistent delivery times.
* Carting routes show higher variability due to multiple stops.

### Delivery Accuracy

* Actual delivery times differ from OSRM predictions on several routes.
* Some corridors consistently experience delays.

### High Traffic Corridors

* Certain source-destination combinations contribute a significant share of total deliveries.
* These corridors require operational optimization.

### Distance Impact

* Delivery time increases with distance, but traffic and route conditions create significant variation.

---

## Business Recommendations

### 1. Improve Route Planning

Monitor corridors with consistently high delivery delays and optimize routing strategies.

### 2. Enhance Delivery Forecasting

Incorporate engineered features such as:

* Delivery Duration
* Route Type
* State
* Distance

into predictive models.

### 3. Optimize High-Volume Corridors

Allocate additional resources to the busiest routes to reduce delays.

### 4. Improve Distance Estimation

Investigate routes where actual distance and OSRM distance differ significantly.

### 5. Strengthen Operational Monitoring

Build dashboards to continuously track:

* Delivery delays
* Route efficiency
* Corridor performance

---

## Project Structure

Delhivery-Feature-Engineering/

├── Dataset/
│   └── delhivery_data.csv

├── Notebook/
│   └── Delhivery_Feature_Engineering.ipynb

├── Images/
│   ├── Distance_Distribution.png
│   ├── Time_Analysis.png
│   ├── Corridor_Analysis.png
│   ├── Correlation_Heatmap.png
│   └── Outlier_Analysis.png

├── Reports/
│   └── Delhivery_Business_Report.pdf

└── README.md

---

## Results

The project successfully transformed raw logistics data into meaningful business features, enabling deeper operational analysis and preparing the dataset for predictive modeling.

The findings provide actionable insights for route optimization, delivery forecasting, and logistics efficiency improvement.

---

## Skills Demonstrated

* Feature Engineering
* Data Cleaning
* Data Aggregation
* Outlier Detection & Treatment
* Exploratory Data Analysis (EDA)
* Statistical Analysis
* One-Hot Encoding
* Data Standardization
* Logistics Analytics
* Python Programming

---

## Author

Vaishnavi Kothur
