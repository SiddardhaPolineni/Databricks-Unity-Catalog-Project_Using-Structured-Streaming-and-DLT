# Fitness_Analysis_Using_Databricks-Unity-Catalog-Project-and-Structured-Streaming
Fitness Tracking or Analysis of an user

## Introduction
This Data Engineering project is focused on building a scalable data platform to track, analyze, and optimize users gym workout sessions using data collected from various fitness devices (e.g., smartwatches, heart rate monitors, motion sensors, and IoT-enabled gym equipment). The platform collects real-time workout data, processes it, and provides actionable insights to improve users fitness journeys. These devices are collabrated with registered Gym or Workout centers and the users workout sessions data tracked on daily basis for better insights. 

## Architecture


## Tech Stack
1. Programming Language: Python3, PySpark, Spark Structured Streaming
2. Azure Cloud:
   - Data Factory
   - Databricks
   - Unity Catalog
   - ADLS Gen2
   - Azure DevOps for CI/CD
  
## Approach and Analysis
-   Enabled unity catalog for data governance and created respective catalogs for dev, qa and prod.
   
-   Move the user registration and login/logout session data from Azure SQL database to ADLS Gen 2 using Azure Data Factory (ADF)

-   The data from Gym or Training centers was consumed from Kafka as three topics 1. user profile 2. BPM Stream 3. workout sessions

-   The 5 datasets were staged into ADLS Gen2 and created external locations and granted privelages to access the data from databricks workspace.

-   Created three bronze tables using 5 datasets. The three topics data from kakfa is multiplexed into one table to create Multiplex bronze table.

-   Implemented Incremental Ingestion process using Databricks Autoloader

-   Implemented necessary transformations, removing duplicate records and implementing CDC in silver tables.

-   Leveraged watermarking startegy to handle the late coming data.

-   Configured the code to run either in a batch mode or in a continous mode.

-   Developed DDL scripts to create bronze and silver tables and gold views in a schema 

-   Leveraged Azure GIT Repos for version controlling.

-   Created CI/CD pipeline to streamline the deployment process from one env to another.

-   Implemented Integration testing and configured in the release pipeline.
