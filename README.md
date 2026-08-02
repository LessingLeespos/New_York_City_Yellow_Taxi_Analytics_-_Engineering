# NYC Yellow Cab Performance & Mobility Pipeline (Microsoft Fabric)
![NYC Taxi Dashboard](/screenshots/01Dashboard_NYC_TaxiData.PNG)

A cloud data engineering and analytics solution built in **Microsoft Fabric**. This project orchestrates an **ELT** workflow using **Data Factory Pipelines, Dataflows Gen2, Lakehouses, Warehouses, and Stored Procedures** to process millions of New York City Yellow Taxi trips into an interactive Power BI Semantic Model.

## Architecture & Data Flow
The project implements a multi-stage **Medallion Architecture** to separate raw data ingestion, transformation, staging, and high-performance reporting layers.

[ NYC TLC Public Source ]
           │
           ▼
 [ Bronze Layer ]
 Dataflows Gen2 / Lakehouse (`lk_TaxiData`)
(Raw ingestion & initial schema mapping)
           │
           ▼
 [ Silver Layer ]
 Staging Pipelines (`pipeline_nyctaxi` / `df_processing_nyctaxi`)
 (Dynamic date checks, outlier cleanup via Stored Procedures)
           │
           ▼
  [ Gold Layer ]
  Data Warehouse (`wh_NYCTaxi`) & Semantic Model (`sm_yellow_nyctaxi`)
  (Star schema modeling, business aggregation tables)
           │
           ▼
 [ Visualization ]
 Power BI Performance Dashboard

## Dashboard Highlights & Analytics
The New York City's Yellow Cab Metrics Performance Dashboard provides operational visibility across key revenue and volume metrics:

-Executive KPIs: Tracks aggregate volume (6.23M Total Passengers) and revenue ($210.89M Total Fare Amount).
-Payment Distribution: Visualizes volume trends by payment type, credit card dominant usage (~85.26%) alongside cash (~12.21%), chargebacks, and disputes.
-Geospatial & Borough Demand: Ranks passenger counts by origin and destination boroughs, isolating core corridors like Manhattan (5.48M pickups) and Queens (677K drop-offs).
-Date Range Filtering: Interactive temporal slicing across pickup windows.

High frequency temporal tracking data transformed urban transit by converting physical passenger movement into real-time geospatial telemetry, allowing platforms to dynamically rebalance supply, implement surge pricing, and minimize deadhead time. This algorithmic efficiency enabled app services to capture the market, outpace traditional street models, and expand mobility into historically underserved outer boroughs successfully capturing market share even amidst strict New York City regulatory hurdles and fleet caps.

Despite heavy market disruption from digital competitors, the traditional Yellow Cab remains an essential fixture of New York City transit. In hyperdense corridors like Midtown Manhattan and airport hubs, physical street hailing continues to outperform app dispatch in speed by avoiding waiting latency. Combined with regulated, nonsurge rate structures and an iconic cultural identity, the Yellow Cab maintains a resilient operational niche within the city's broader transit ecosystem.
