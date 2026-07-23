# cr-seismic-activity-analytics
## Project Overview
Costa Rica is located on the highly active subduction zone between the Cocos and Caribbean plates, making it one of the most seismically dense regions in the world. 
This project implements a fully automated, production-grade **End-to-End Data Engineering Pipeline** designed to ingest, process, and analyze historical and real-time earthquake data from the United States Geological Survey (USGS) API.

The primary objective of this architecture is to identify seismic patterns over the last 26 years and measure the frequency, location, and human impact of earthquakes that cause structural damage or significant public disruption (Magnitudes ≥ 4.0).

## Tech Stack & Architecture
* **Orchestration & Compute:** Databricks Community / Enterprise
* **Data Governance:** Unity Catalog (Managed Volumes for Raw Ingestion)
* **Ingestion Engine:** PySpark Auto Loader (`cloudFiles` structured streaming)
* **Storage Format:** Delta Lake (ACID Transactions)
* **Architecture Design:** Medallion Architecture (Landing ➔ Bronze ➔ Silver ➔ Gold)
* **Data Source:** USGS Earthquake Catalog API (FDSN Event Web Service)


# Research Hypotheses & Analytical Objectives

To guide the Exploratory Data Analysis (EDA) and prevent post-hoc bias, this project formalizes three core hypotheses based on regional geodynamics and statistical seismology:

1. **Spatial Severity (Hypothesis 1):** Events along the Pacific subduction boundary (west of 85.0° W) exhibit higher average magnitudes and greater focal depth variance than inland crustal events.
2. **Magnitude Scale Decay (Hypothesis 2):** Micro and minor earthquakes (Magnitude < 4.0) comprise at least 85% of total catalog volume, following an exponential frequency distribution.
3. **Temporal Swarm Dynamics (Hypothesis 3):** High-magnitude triggers (Magnitude >= 5.5) initiate localized temporal clusters, causing a statistically significant increase (over 200%) in event frequency within the subsequent 72 hours.