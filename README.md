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
